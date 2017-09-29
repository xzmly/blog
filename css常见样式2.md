### 1.text-align: center的作用是什么，作用在什么元素上？能让什么元素水平居中
- 作用在行内元素上，实现行元素居中。
***

### 2. IE盒子模型和W3C盒子模型有什么区别？
- IE 的盒子模型content 中包含了border和padding

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-07397aca944de696.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- W3C的盒子模型content是不包括border和padding的

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-66e178911d9516d9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
***


### 3. ```{ box-sizing: border-box;}```的作用是什么？
- 转换为IE的盒子模型，就是内容包括了border和padding
### ```{ box-sizing: content-box;}```的作用是什么？
- 默认值了，就是普通的W3C盒子模型。
***

### 4.line-height: 2和line-height: 200%有什么区别?
- line-height: 200%：当前字体尺寸的百分之两百设置行间距。
- line-height: 2： 数字会与当前的字体尺寸相乘来设置行间距。
***


### 5.inline-block有什么特性？如何去除缝隙？高度不一样的inline-block元素如何顶端对齐?
- inline-block：对象为内联对象，但是对象的内容可以作为块对象操作。(简单认为，可以设置大小的内联元素)
- 如何去除缝隙：
> 1.你可以把标签与标签之间的空格全部删除，但是这样不美观。
> 2.在父元素设置，```font-size：0；```然后在你想设置的元素上再重新设置```font-size：；```(简单点说就是将空白字符的高度都设置为0)；
> 3.高度不一样的inline-block元素如何顶端对齐：```vertical-align: top;```
***

### 6.CSS sprite 是什么?
- 简称雪碧图
- 你上去淘宝看看那些一个一个的icon就是雪碧图
- 优点：减少网页的http请求，从而大大的提高页面的性能

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-e563117f790a5e71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
***

### 7.让一个元素"看不见"有几种方式？有什么区别?
|方法|区别|
-|-
|opacity：0；|改变了透明度，让你看不见了。 还存在|
|display: none;|会让选中的元素直接删除；|
|visibility：hidden；|类似于 opacity  还存在|
|background：rbga(0，0，0，0.2)|也是改变背景颜色，和透明度 还存在|
