### JavaScript 定义了几种数据类型? 哪些是原始类型?哪些是复杂类型?原始类型和复杂类型的区别是什么?
1.JavaScript 定义了几种数据类型?
 一共有6种，分别是：
> 数值(number)：整数和小数；
> 字符串(string)：字符组成的文本；
> 布尔值(boolean)：true（真），flase（假）；
> underfined：表示未定义，不存在。
> null：空值，但不代表不存值。
> 对象（object）：各种值的组合集合；

2.哪些是原始类型?
数值，字符串，布尔值，称为原始类型的值，也叫基本类型。即它们是最基本的数据类型，不能再细分。

3.哪些是复杂类型？
对象就是复杂类型，也叫做引用类型，因为对象往往是多个原始类型的值的合成，可以看作是一个存放各种值得容器。

对象细分为:
> - 侠义的对象。
> - 数组（Array）
> - 函数（function）
> - 正则表达式

- ps：underfined和null一般看作是两个特殊的值。

4.原始类型和复杂类型有什么区别？
- 基本类型一般存放于栈内存，是一个单一的值。
- 引用类型存放于堆内存中。用一个变量，放在栈内存中，指明它的地址。是一个包含各种值得容器。

### typeof和instanceof的作用和区别?
- typeof： 一般用来检测基本类型是什么类型，例如：```typeof 123``` 得到的值就是```number```。可是如果检测引用类型的话就会返回```object```，不能明确区分到底是```{}``` 还是数组```[]```。(检测函数的时候会返回```funtion```)

ps：```typeof null``` 是```object```，```typeof underfined``` 得到的是```underfined```。

- instanceof：用来检测对象到底是数组```[]```，还是```{}```。

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-31458c40d14e608c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 如何判断一个变量是否是数字、字符串、布尔、函数?
> ```typeof 123  //number```
```typeof 'hello'  //string```
```typeof true  //boolean```
```function f(){} typeof f  //function```

### NaN是什么? 有什么特别之处?
- NaN本身是一个Number，基本类型。（我是一个数据类型，但是我不是一个有效的数据！！！！！！！！！！！！）
- NaN含义是Not a Number，表示非数字，NaN和任何值都不相等，包括自己。

### 如何把非数值转化为数值?
- parseInt()  （如果遇到小数点，会把小数向下约等于，转换为整数。 ）
```parseInt('123') // 123```
```parseInt('3.4') // 3```
- parseFloat() （如果遇到小数，会保留小数，转换为数据类型。）
``` parseFloat('3.4') // 3.4```

### ==与===有什么区别?
- ==： 是近似等于。 == 在比较的时候可以转自动换数据类型
- ===： 是绝对等于。 === 严格比较，不会进行自动转换，要求进行比较的操作数必须类型一致，不一致时返回flase。

### break与continue有什么区别？
- break是立即跳出循环。
- continue 是跳出本次循环。执行下次循环。

### void 0 和 undefined在使用场景上有什么区别?
- void 会执行后面的表达式并返回 undefined，是一个纯正的undefined；
- underfined可以在局部作用域被赋值，复写。
