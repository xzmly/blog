.toUpperCase() 变成大写
~~~
var a="string"
var b=a.toUpperCase()
console.log(b)//"STRING"
~~~
.toLowerCase() 变成小写
~~~
var a="STRING"
var b=a.toLowerCase()
console.log(b)//"string"
~~~
.split() 以括号里面的内容为分界点，让字符串变为数组
~~~
例子1：
var a="string-ing"
var b=a.split("-")
console.log(b)//["string","ing"]

例子2：
var a="string"
var b=a.split()//可以不写东西
console.log(b)//["string"]

例子3
var a="string"
var b=a.split("")
console.log(b)//["s", "t", "r", "i", "n", "g"];
~~~
.join() 让数组以括号里面的内容合并成一个字符串
~~~
var a=[1,2,3,4,5,6]
var b=a.join("")
console.log(b)//123456

例子2：
var a=[1,2,3,4,5,6]
var b=a.join()
console.log(b)//1,2,3,4,5,6
~~~
substr() 获取字符串指定的部分
~~~
var a="string"
var b=a.substr(1,2)//获取了从1开始的后面2个字符串，包括1
////如果省略第二个参数，会自动获取到最后

console.log(b)//tr
console.log(a)//"string"  这个方法不会对原字符串做出任何修改
~~~
substring() 获取字符串指定的部分
~~~
var a="string"
var b=a.substring(1,2)//获取了从1开始的后面2个字符串，这个不包括1
//如果省略第二个参数，会自动获取到最后

console.log(b)//j
console.log(a)//"string"  这个方法不会对原字符串做出任何修改
~~~
reverse()把数组翻转
~~~
var a=[1,2,3,4,5];
var b=a.reverse()
console.log(b)//[5,4,3,2,1]
~~~
toString//把数组变成字符串，就用逗号隔开
~~~
var a=[1,2,3,4,5,6]
var b=a.toString()
console.log(b)//1,2,3,4,5,6
~~~
splice() 切取数组的值（会改变原来的数组）
~~~
var a=[1,2,3,4,5,6]
var b=a.splice(0,1,2)//从0开始索引，窃取1位数，会包括0，然后把窃取的位置添加2
console.log(b)//[1]
console.log(a)//[2,2,3,4,5,6]
~~~
slice()窃取数组的元素，不会改变原数组。
~~~
var a=[1,2,3,4,5,6]
var b=a.slice(0,3)包括第0位，从第0位开始窃取后面的三个元素。不会改变原数组
console.log(b)//[1,2,3]
console.log(a)//[1,2,3,4,5,6]
~~~
push() / pop() 从数组后面添加元素 / 从数组后面删除元素 （都会改变原数组）
~~~
var a=[1,2,3,4,5,6]
a.push(7)
console.log(a)//[1,2,3,4,5,6,7]
a.pop()
console.log(a)//[1,2,3,4,5,6]
~~~
unshift() / shift() 从数组前端添加元素 / 从数组前端删除元素 （都会改变原数组）
~~~
var a=[1,2,3,4,5,6]
a.unshift(7)
console.log(a)//[7,1,2,3,4,5,6]
a.shift() 
console.log(a)//[1,2,3,4,5,6]
~~~
