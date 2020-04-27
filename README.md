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
 + [Глубокое сравнение](#глубокое-сравнение)
 + [Every и some](#every-и-some)
 + [Векторный тип](#векторный-тип)
 + [Ещё одна ячейка](#ещё-одна-ячейка)
 + [Замыкание](#замыкание)
 + [Свертка](#свертка)


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
function reverseArray(bar){
  let foo = []
  for(let i = bar.length - 1; i >= 0 ; i-- ){
    foo.push(bar[i])
  }
  return foo

reverseArray(names)
```
и
```
function reverseArrayInPlace(bar){
  for(let i = 0; i <= Math.floor((bar.length - 1)/2); i++){
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

## Глубокое сравнение

```
Оператор == сравнивает переменные объектов, проверяя, ссылаются ли они на один объект. 
Но иногда полезно было бы сравнить объекты по содержимому.Напишите функцию deepEqual, 
которая принимает два значения и возвращает true, только если это два одинаковых значения или это объекты,
свойства которых имеют одинаковые значения, если их сравнивать рекурсивным вызовом deepEqual.
Чтобы узнать, когда сравнивать величины через ===, а когда – объекты по содержимому,
используйте оператор typeof. Если он выдаёт “object” для обеих величин, значит нужно делать
глубокое сравнение. Не забудьте об одном дурацком исключении, случившемся из-за исторических 
причин: “typeof null” тоже возвращает “object”.
```

<details><summary>💡</summary>
<p>

```
 function deepEqual(foo, bar){
  if(foo && typeof foo === 'object' && bar && typeof bar === 'object' ) {
    for(key in foo){
      if(bar.hasOwnProperty(key)){
       const isEqual = deepEqual(foo[key], bar[key])
       if(!isEqual) return false
      } else {
        return false
      }
    }
    for(key in bar){
      if(!foo.hasOwnProperty(key)) return false
    }
    return true
  }   
  else if (typeof foo !== 'object' && typeof bar !== 'object') {
    if(foo === bar){
      return true
    }
  }
  return false
}
```
</p>
</details>

## Свертка

```
Используйте метод reduce в комбинации с concat для свёртки массива массивов в один массив,
у которого есть все элементы входных массивов.
```

<details><summary>💡</summary>
<p>

```
let foo = [[1, 2, 3], [4, 5], [6]]

let result = foo.reduce((accum, current) => accum.concat(current),[])
```
</p>
</details>


## Every и some


```
У массивов есть ещё стандартные методы every и some. Они принимают как аргумент некую функцию,
которая, будучи вызванной с элементом массива в качестве аргумента, возвращает true или false.
Так же, как && возвращает true, только если выражения с обеих сторон оператора возвращают true,
метод every возвращает true, когда функция возвращает true для всех элементов массива.
Соответственно, some возвращает true, когда заданная функция возвращает true при работе хотя бы 
с одним из элементов массива. Они не обрабатывают больше элементов, чем необходимо – например,
если some получает true для первого элемента, он не обрабатывает оставшиеся.
Напишите функции every и some, которые работают так же, как эти методы, только принимают
массив в качестве аргумента.
```

<details><summary>💡</summary>
<p>

```

function every(bar, foo) {
for (var i = 0; i < bar.length; i++) {
if (!foo(bar[i]))
return false;
}
return true;
}

function some(bar, foo) {
for (var i = 0; i < bar.length; i++) {
if (foo(bar[i]))
return true;
}
return false;
}
 ```
</p>
</details>

## Векторный тип


```
Напишите конструктор Vector, представляющий вектор в двумерном пространстве.
Он принимает параметры x и y (числа), которые хранятся в одноимённых свойствах.
Дайте прототипу Vector два метода, plus и minus, которые принимают другой вектор в качестве 
параметра, и возвращают новый вектор, который хранит в x и y сумму или разность 
двух (один this, второй — аргумент)
```

<details><summary>💡</summary>
<p>

```
function Vector(x,y){
  this.x = x;
  this.y = y;
}

Vector.prototype.plus = function(vector) {
  let newX = this.x + vector.x;
  let newY = this.y + vector.y;
  return new Vector(newX,newY)
};

Vector.prototype.minus = function(vector) {
  let newX = this.x - vector.x;
  let newY = this.y - vector.y;
  return new Vector(newX,newY)
};
 ```
</p>
</details>

## Ещё одна ячейка


```
Создайте тип ячейки StretchCell(inner, width, height), соответствующий интерфейсу 
ячеек таблицы из этой главы. Он должен оборачивать другую ячейку (как делает 
UnderlinedCell - из примера книги), и убеждаться, что результирующая ячейка имеет как
минимум заданные ширину и высоту, даже если внутренняя ячейка была бы меньше.
```

<details><summary>💡</summary>
<p>

```
unction repeat(string, times) {
	var result = "";
	for (var i = 0; i < times; ++i)
		result += string;
	return result;
}

function TextCell(text) {
	this.text = text.split("\n");
}

TextCell.prototype.minWidth = function() {
	return this.text.reduce(function(width, line) {
		return Math.max(width, line.length);
	}, 0);
};
TextCell.prototype.minHeight = function() {
	return this.text.length;
};
TextCell.prototype.draw = function(width, height) {
	var result = [];

	for (var i = 0; i < height; ++i) {
		var line = this.text[i] || "";
		result.push(line + repeat(" ", width - line.length));
	}
	return result;
};


function StretchCell(inner, width, height) {
	this.inner = inner;
	this.width = width;
	this.height = height;
}

StretchCell.prototype.minWidth = function() {
	return Math.max(this.width, this.inner.minWidth());
};
StretchCell.prototype.minHeight = function() {
	return Math.max(this.height, this.inner.minHeight());
};
StretchCell.prototype.draw = function(width, height) {
	return this.inner.draw(width, height);
}
 ```
</p>
</details>


## Замыкание

```
написать функцию, add, чтобы вызов add(1)(2) вернул 3 
```

<details><summary>💡</summary>
<p>

```
function add(a) {
  return function(b) {
    return a + b;  
  };
}
```
</p>
</details>



