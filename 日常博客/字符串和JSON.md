### 对于 HTTP 协议而言，HTML、CSS、JS、JSON 的本质都是什么？
对于HTTP而言：
- HTML就是符合HTML语法的字符串。
- CSS就是符合CSS语法的字符串。
- JS就是符合JS语法的字符串。
- JSON就是符合JSON语法的字符串。

###  什么是 JSON格式数据？JSON格式数据如何表示对象？window.JSON 是什么？
- 首先什么是JSON？
  - JSON就是一种轻量级的数据交换格式（javaScript Object Notation）

  - JSON值有：
>string 
number 
object 
array 
true 
false 
null
没有函数

#### 什么是 JSON格式数据？
- son(javascript object notation)的缩写是一种用于数据交换的文本格式，目的是取代繁琐的xml。具有书写简单，一目了然，符号javascript原生语法，可以由解释引擎直接处理，不用另外添加解析代码。

#### JSON格式数据如何表示对象？
- JSON 数据的书写格式是：名称/值对，名称/值对组合中的名称写在前面（在双引号中），值对写在后面(同样在双引号中)，中间用冒号隔开：
~~~
var json2 = [
    {"name": "cwb", "age": "22"},
    {"name": "cwh", "age": "18"}
]
~~~

#### 什么事window.JSON?
- window.JSON就是浏览器对JSON对象的支持，IE浏览器需在IE8及以上才支持JSON对象，其他浏览器都支持JSON对象。


### 11、如何把JSON 格式的字符串转换为 JS 对象？如何把 JS对象转换为 JSON 格式的字符串?
1.如何把JSON 格式的字符串转换为 JS 对象？(IE8以上才能用)
```JSON.parse()```把JSON字符串转换为JS相对的对象
~~~
var str='{"name":"cwh"，"age":30}'
var obj=str.parse(str)
~~~
2.如何把 JS对象转换为 JSON 格式的字符串?
```JSON.stringIfy()```把JSON字符串转换为JS相对的对象
~~~
var obj={"name":"cwh","age":18}
var str=JSON.stringify(obj)
~~~
