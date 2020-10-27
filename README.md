
# JavaScript Best Practice
---
### 1. Избегайте Глобальных Переменных

Сведите к минимуму использование глобальных переменных.
Сюда входят все типы данных, объекты и функции.
Вместо этого используйте локальные переменные.

 + good example
```
function nameFunction() {
	let x = 5;
	z = x + y;
}
```
+ bad example
```
let x = 5;
function nameFunction() {
	z = x + y;
}
```
### 2. Не используйте new... для создания нового объекта, массива, функции и тд
+ Используйте {} вместо new Object()
+ Используйте "" вместо new String()
+ Используйте 0 вместо new Number()
+ Используйте false вместо new Boolean()
+ Используйте [] вместо new Array()
+ Используйте function() {} вместо new Function()

+ example
```
var x1 = {}; // new object
var x2 = ""; // new primitive string
var x3 = 0; // new primitive number
var x4 = false; // new primitive boolean
var x5 = []; // new array object
var x6 = function(){}; // new function object
```

### 3.  Не передавайте строку в "SetInterval" или " SetTimeOut"

Никогда не передавайте строку в SetInterval и SetTimeOut. Вместо этого передайте имя функции.

+ bad example
```
setInterval(
"document.getElementById('container').innerHTML += 'My new number: ' + i", 3000
);
```
 + good example
```
setInterval(someFunction, 3000);
```

### 4. Длинный список переменных? Опустите Ключевое слово "Var" и используйте вместо него запятые

 + good example
```
var someItem = 'some string',
    anotherItem = 'another string',
    oneMoreItem = 'one more string';
```
+ bad example
```
var someItem = 'some string';
var anotherItem = 'another string';
var oneMoreItem = 'one more string';
```
### 5. Распространенной ошибкой в программах JavaScript является

 использование объекта, когда требуется массив, или массива, когда требуется объект. Правило простое:когда имена свойств являются небольшими последовательными целыми числами, вы должны использовать массив. В противном случае используйте объект."- Дуглас Крокфорд

 +  example
```
var a = ['Joe','Plumber'];

a[0] = "Joe";
a[1] = 'Plumber';
```
+ example
```
let users = {
	firstName: "John",
	lastName: "Doe"
};
```
### 6. Всегда, Всегда Используйте Точки С Запятой

Технически, большинство браузеров позволят вам уйти от пропуска точек с запятой.
Тем не менее, это очень плохая практика, которая потенциально может привести к гораздо большим и труднодоступным проблемам.


+ good example
```
let someItem = 'some string';
function doSomething() {
  return 'something';
}
```
+ bad example
```
let someItem = 'some string'
function doSomething() {
  return 'something'
}
```
### 7. Используйте === вместо ==

== оператор сравнения всегда преобразует (в соответствующие типы) перед тем, как сравнивает.
=== Оператор заставляет сравнивать значения и тип:


+  example
```
0 == ""; // истинный
1 == "1"; // истинный
1 = = истинный; // истинный

0 === ""; // ложный
1 === "1"; // ложный
1 = = = истинный; // ложный
```

### 8. Поместите Скрипты в нижней части страницы

Помните-основная цель состоит в том, чтобы сделать загрузку страницы как можно быстрее для пользователя. При загрузке скрипта браузер не может продолжать работу до тех пор, пока не будет загружен весь файл. Таким образом, пользователю придется ждать дольше, поэтому поместите Скрипты в нижней части страницы, перед </body>.

+ good example
```
<body>

<script type="text/javascript" src="path/to/file.js"></script>
<script type="text/javascript" src="path/to/anotherFile.js"></script>
</body>
</html>

```
+ bad example
```
<head>

<script type="text/javascript" src="path/to/file.js"></script>
<script type="text/javascript" src="path/to/anotherFile.js"></script>
</head>
```
### 9. Прокомментируйте Свой Код

Всегда, всегда комментируйте важные разделы вашего кода.

+ good example
```
// it's the main part of my js code

if (json.bio !== null) {
		bio.innerHTML = json.bio;
		} else {
		bio.innerHTML += "Информация о пользователе не доступна."
		}
```
### 10. Используйте отладчик кода

Просто вставьте свой скрипт, и он быстро отсканирует все заметные проблемы и ошибки в вашем коде.

+ good example
```
JSLint это отладчик, написанный Дугласом Крокфордом.
```


