### 1.块级元素和行内元素分别有哪些？
块级元素：div，h1~h6，table，form，header， footer，nav，ul，li，ol，dl。。。。。
行内元素：a，input，span，i，img，strong， select。。。。。
### 2.动手测试并列出4条以上的特性区别。
|块级元素|行内元素|
-|-
|没有设置宽度的情况下，默认占据一整行|内容有多宽，我就有多宽|
|可以随便设置宽高|不可以|
|随便设置padding，margin|padding和margin只可以设置左右|
|可以包裹块级元素，行内元素|我只能包裹文本，和行内元素|

### 3.什么是 CSS 继承? 哪些属性能继承，哪些不能？
CSS继承，就是子元素继承了父元素的属性。

|能继承|不能继承|
-|-
|letter-spacing|height|
|word-spacing|min-height|
|white-space|max-height|
|line-height|width|
|color|min-width|
|font|max-width|
|font-style|float|
|font-family|position|
|text-align|overflow|
|text-indent|vertical-align|
|font-weight|clear|
|等等等等|等等等等|

### 4.如何让块级元素水平居中？如何让行内元素水平居中?
块级元素水平居中：margin：0 auto；
行内元素水平居中：text-align：center；

### 5.单行文本溢出加.......如何实现？
E{
white-space:nowrap;
overflow:hidden;
text-overflow;
}

### 6.px, em, rem 有什么区别
- px：固定尺寸；
- em： 相对于当前对象内文本的字体尺寸
- rem： 相对于HTML的相对大小

### 7.解释下面代码的作用?为什么要加引号? 字体里\5b8b\4f53代表什么?
body{
  font: 12px/1.5 tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif;
}

1.设置body字体大小为12px，行高是字体1.5倍的像素值，后面则是第一到第五字体，用逗号隔开，如果第一个你电脑没有，则运行第二个。
2.加引号是因为，字体间有空格，这样会识别为不同的两个单词，所以加空格。
3.字体那些代码代表“宋体”


![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-cfd4c8f3ff1fa676.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ps:在浏览器console里输入escape（"你想要的字体编码"），就能出现像想要的代码
记住将%u改成/。
