8 - тестовый проект, использована структура папок <a href="https://feature-sliced.design/ru/docs/reference/layers">FSD</a> архитектуры, для данной верстки too much, просто тренировка

# DIgineticaTest

1.Каким будет результат следующей операции на языке JavaScript: [1, 2, 3] + [4, 5, 6]. Почему был получен такой результат?<br/>
ОТВЕТ: результат будет 1,2,34,5,6 js приведет все к строке и объединит .<br/>

2.Дано выражение:<br/>
var a = {b: 1};<br/>
var b = a;<br/>
b.b = 2;<br/>
console.log(a);<br/>
Что будет выведено в консоли? Почему был получен такой результат?<br/>
ОТВЕТ: b.2 в выражении копируется ссылка на объект, а не сам объект, a и b указывают на один и тот же объект, для неглубокого копирования объекта используется Object.assign(), для глубокого копирования нужно писать свою реализацию, либо взять готовое решение из lodash, или structuredClone()<br/>

3.Написать регулярное выражение, совпадающее с числом с плавающей точкой с точностью до 3 знака после запятой.<br/>
ОТВЕТ: /^\d+(?:[.,]\d{2})?$/<br/>

4.Написать регулярное выражение, по которому определяется является ли строка ссылкой. Объяснить, как оно работает.<br/>
ОТВЕТ: /https?:\/\/(w{3})?\.?\w+\.\w+/, после s квантификатор ?(означающий, что s необязателен), \/ экранирование слеша, w{3}? (необязательные 3 буквы w, за ними точка, далее идет n букв для домена <br/>2ур, далее знак точки и n букв для домена первого уровня.<br/>

5.Каким будет значение переменной text после выполнения данного JavaScript кода? <br/>
function setText(message) { <br/>
text = message;<br/>
}<br/>
var text = 'Текст';<br/>
setText('Сообщение');<br/>
Опишите, почему получился такой результат.<br/>
ОТВЕТ:значение переменной text = сообщение ,в функцию setText передали аргумент,setText сначала ищет инициализированную переменную text в своей области видимости,далее, если не находит, берет из внешней области видимости и присваивает ей параметр message<br/>

6.Написать функцию для получения список всех артикулов товаров в консоли браузера на странице https://groupprice.ru/categories/jenskaya-odejda?referer_from=main_catalog<br/>
<br/>
ОТВЕТ:<br/>
const product = document.querySelectorAll('.\_product'); <br/>
product.forEach (elem => console.log(elem.getAttribute("data-id")));<br/>

7.ОТВЕТ:<br/>
Написать функцию для получения всех характеристики товара в консоли браузера в виде объекта в формате attributeName: value на странице <br/>
const names = document.querySelectorAll(".parameter-name");<br/>
const arrName = [];<br/>
names.forEach((elem) => arrName.push(elem.innerText.trim()));<br/>
const values = document.querySelectorAll(".parameter-value ");<br/>
let arrValue = [];<br/>
values.forEach((elem) => arrValue.push(elem.innerText));<br/>
console.log(Object.assign(...arrName.map((n, i) => ({ [n]: arrValue[i] }))));
