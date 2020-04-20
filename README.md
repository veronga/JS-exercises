#  :books: ЗАДАЧИ ПО JAVASCRIPT 

### ✨ Здесь собраны задачи по JS и моё решение к ним
***

#  СПИСОК ЗАДАЧ

 + [Треугольник](#треугольник)
 + [FizzBuzz](#fizzbuzz)
 + [Шахматная доска](#шахматная-доска)
 + [Минимум](#минимум)
 + [Рекурсия](#рекурсия)
 + [Считаем бобы](#считаем-бобы)
 + [Сумма диапазона](#сумма-диапазона)
 + [Обращаем массив вспять](#обращаем-массив-вспять)


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
</p>
</details>


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

</p>
</details>

## Минимум


```
 Напишите функцию min, принимающую два аргумента, и возвращающую минимальный из них.
```

<details><summary>💡</summary>
<p>

```
function min(a,b){
  if(a > b){
  return b
 }
  return a
}
 min(66,745)
 ```
</p>
</details>

## Рекурсия
```
Ноль чётный. Единица нечётная. У любого числа N чётность такая же, как у N-2.
Напишите рекурсивную функцию isEven согласно этим правилам. Она должна принимать число 
и возвращать булевское значение. Потестируйте её на 50 и 75. Попробуйте задать ей -1. 
```

<details><summary>💡</summary>
<p>

```
function isEven(n){
  if(n === 0){
    return true
  } else if (n === 1) {
    return false
  } else if (n < 0){
    return isEven(n + 2)
  }
  return isEven(n - 2)
}

isEven(50)
```
</p>
</details>

## Считаем бобы
```
Напишите функцию countBs, которая принимает строку в качестве аргумента,
и возвращает количество символов “B”, содержащихся в строке.Затем напишите функцию countChar,
которая работает примерно как countBs, только принимает второй параметр — символ,
который мы будем искать в строке (вместо того, чтобы просто считать количество
символов “B”). Для этого переделайте функцию countBs.
```

<details><summary>💡</summary>
<p>

```
 function countChar(string,letter){
  let counter = 0;
	for (let i = 0; i < string.length; i++) {
	  if (string[i] === letter) {
      counter++
    }
  }
    return counter
  }

countChar("аmbassador",'s')
```
</p>
</details>

## Сумма диапазона
```
Напишите функцию range, принимающую два аргумента, начало и конец диапазона, и возвращающую массив, 
который содержит все числа из него, включая начальное и конечное.Затем напишите функцию sum,
принимающую массив чисел и возвращающую их сумму.
```

<details><summary>💡</summary>
<p>

```
function range(a,b){
  let rangeOfNumbers = []
  for(; a <= b; a++){
    rangeOfNumbers.push(a)
  }
  return rangeOfNumbers
}
```
и
```

function sum(range){
  let sum = range.reduce((accum,current) => accum + current)
  return sum
}

sum(range(5,9))
```


</p>
</details>

## Обращаем массив вспять
```
Напишите две функции, reverseArray и reverseArrayInPlace. Первая получает массив как аргумент
и выдаёт новый массив, с обратным порядком элементов. Вторая работает как оригинальный метод 
reverse – она меняет порядок элементов на обратный в том массиве, который был ей передан в качестве 
аргумента. Не используйте стандартный метод reverse.
```

<details><summary>💡</summary>
<p>

```
let names = ["Вероника","Влад","Женя","Катя"]
```
```
function reverseArray(foo){
  let foo = []
  for(let i = arr.length - 1; i >= 0 ; i-- ){
    foo.push(arr[i])
  }
  return foo

}
reverseArray(names)
```
и
```
function reverseArrayInPlace(bar){
  for(let i = 0; i <= Math.floor((arr.length - 1)/2); i++){
    let elem = bar[i]
    bar[i] = bar[bar.length - 1 - i]
    bar[bar.length - 1 - i] = elem
  }
  return bar
}
 
reverseArrayInPlace(names)
```

</p>
</details>


