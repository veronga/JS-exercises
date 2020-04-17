#  :books: ЗАДАЧИ ПО JAVASCRIPT 

### ✨ Здесь собраны задачи по JS и моё решение к ним
***

#  СПИСОК ЗАДАЧ

 + [Треугольник](#треугольник)
 + [FizzBuzz](#fizzbuzz)
 + [Шахматная доска](#шахматнаядоска)


# РЕШЕНИЯ

## Треугольник
```
Напишите цикл, который выводит такой треугольник:
#
##
###
####
#####
######
#######
```

<details><summary>💡</summary>
<p>

```
let i = "#";
while (i.length <= 7){
    console.log(i)
    i = i + "#"
}
```
или
```
for (let a = "#"; a.length <= 7; a = a + "#") {
  console.log(a)
}
```


</p>
</details>

## FizzBuzz
```
Напишите программу, которая выводит через console.log все числа от 1 до 100, с двумя исключениями. 
Для чисел, нацело делящихся на 3, она должна выводить ‘Fizz’, а для чисел, делящихся на 5 (но не на 3)
– ‘Buzz’.Когда сумеете – исправьте её так, чтобы она выводила «FizzBuzz» для всех чисел,
которые делятся и на 3 и на 5.
```

<details><summary>💡</summary>
<p>

```
 for (let i = 0; i <= 100; i++) {
  if(i % 3 === 0 && i % 5 === 0){
    console.log("FizzBuzz");
  } else if(i % 5 === 0){
    console.log("Buzz");
  } else if(i % 3 === 0){ 
    console.log("Fizz");
  }  else {
    console.log(i);
  }
}
```

## Шахматная доска
```
Напишите программу, создающую строку, содержащую решётку 8х8, в которой линии разделяются
символами новой строки. На каждой позиции либо пробел, либо #.
В результате должна получиться шахматная доска.
# # # #
 # # # #
# # # #
 # # # #
# # # #
 # # # #
# # # #
 # # # #
```

<details><summary>💡</summary>
<p>

```
let board = ""
for  (let col = 0; col <= 7; col++){
  for (let row = 0; row <= 7; row++) {
    const isRowIndexEven = row % 2 === 0
    const isColIndexEven = col % 2 === 0
    board += (isRowIndexEven && isColIndexEven) || (!isRowIndexEven && !isColIndexEven) ? '#': ' '
 }
  board += '\n'
 }

console.log(board)
```
