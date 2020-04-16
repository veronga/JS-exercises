#  ЗАДАЧИ ПО JAVASCRIPT 

#### ✨ Здесь собраны задачи по JS и моё решение к ним
***

#  СПИСОК ЗАДАЧ

1. [Треугольник](#треугольник)

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
