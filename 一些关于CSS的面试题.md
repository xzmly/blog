### class 和 id 的使用场景。
- id：多用于页面分块的块级标签上。id是独一无二的！！
- class：用于同一个类别的标签上。定位页面上某一类元素。

### css常见的选择器有哪几种。
1.基础选择器。
2.组合选择器。 
3.属性选择器。   
4.伪类选择器。
5.伪元素选择器。

### 选择器的优先级是怎样的?对于复杂场景如何计算优先级？
- !important>内联>内部>外部
- id>class>伪类>属性>标签>通配符

对于复杂场景如何计算优先级？
>把!important 内联当做是 a
> 把Id当做  b
> 把class 当作 c
> 把伪累，属性，标签，通配符当做 d
例如： 
```style="font-size: 20px;"```      a=1 b=0 c=0 d=0
```#id .class .class```  a=0 b=1 c=2 d=0
```#id .class p```  a=0 b=1 c=1 d=1
> - 先比较a，a大则优先级大，再比较b，b大优先级大，再比较c，如此类推。。。。


### a:link, a:hover, a:active, a:visited 的顺序是怎样的？ 为什么？
- 很多时候a标签会有很多样式，这时候我们就要分清伪类样式的执行顺序。

> 1. 当a标签没有被点击的时候 link 就会处于激活状态。
> 2. 当a标签被点击访问了的时候，visitde就会长期出去激活状态。
>3.  而我们想hover 和 active 都能触发。
>4.  后面的会覆盖前面的。
>5.  hover 是鼠标获得焦点触发，而active是点击触发。
>  6. 自然顺序就是：
1.a:link
2.a:visited
3.a:hover
4.a:active

### 以下选择器是什么意思？？

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-cc8aab70355b7e86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1. 选择了id为header的元素。

2.选择了class为header的元素。

3.选择了class为header里面class为logo的元素。

4.选择了既是class是header  class也是.mabile的元素。

5.选择了class为header 里面的p元素和 class为header 里面的h3元素。

6. 选择了id为header 里面 class为nav 里面的子元素 li。

7.选择了id为header 里面的a元素在鼠标获得焦点是哦胡做出的反应。

8.选择了id为header里面class为logo下面所有的p元素。

9.选择了id为header里面属性为text的input元素。

#### 常用的伪累选择器有哪些？

|标签|意思|
-|-
|```E:first-child```|选择E的父元素里的第一个子元素|
|```E:first-of-type```|选择同类元素中的第一个元素|
|```E:last-child```|选择E的父元素里的最后一个子元素|
|```E:last-of-type```|选择同类元素中的最后一个元素|
|```E:nth-child(n)```|选择E的父元素里的第n个子元素|
|```E:nth-of-type(n)```|选择同类元素中的第n个元素|
|```E:hover```|E元素获得焦点时候干啥|
|```E:active```|E元素被点击时候干啥|
|```E:link```|E元素未被访问的样式|
|```E:visited```|E元素已经访问过的样式|

### ```div:first-child```、```div:first-of-type```、```div :first-child```和```div :first-of-type```的作用和区别 （注意空格的作用）
- ```div:first-child```  选择div的父元素里的第一个div元素
- ```div:first-of-type``` 选择父元素下使用同种标签的第一个子div元素
- ```div :first-child``` 匹配div元素下的第一个子元素
- ```div :first-of-type``` 选择div下的 同类的 第一个元素


### 运行如下代码，解析下输出样式的原因。


![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-2e80c2308fa40463.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- p会变红
- p跟p下面的第一个h3背景颜色会变蓝
- 请看css的内部样式
   1. 第一个选择的是class为item1的元素的父元素的第一个子元素           没错 就是p那就变红啊
   2. 第二个选择的是item1的第一个同类元素   那就看看3个item1  有多少类型  一个p 两个h3  谁是第一个？？？？？背景自动变蓝。。。
