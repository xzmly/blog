### 1.浮动元素有什么特征？对父容器、其他浮动元素、普通元素、文字分别有什么影响?
- 浮动之后的元素将不会再文档的普通流中，可以用float属性控制其左右移动，碰到边框外缘或者碰到其他浮动元素就会停止。

###### 对父容器影响:
如果父元素里全部子元素都是浮动元素，那么父容器会塌陷（因为无法识别里面的元素）。
###### 对其他浮动元素影响:
如果其它元素也设置浮动遇到它会停止，如果父容器宽度撑不起浮动元素，则最后的元素将会换到下一行，换到下一行遇到浮动元素可能会被卡住。
##### 对普通元素影响：
普通元素会识别不了浮动元素，就会产生重叠，遮挡。
##### 对文字有什么影响：
文字不同普通元素，会识别到浮动元素，所以就会被浮动元素隔开，在浮动元素周围围绕。

### 2.清除浮动指什么? 如何清除浮动? 两种以上方法
- 清楚浮动是指 允不允许 设置元素 周围 存在 浮动元素。
##### 清除浮动的方式：
1.在你想不参与浮动的元素上设置```clear：left/right/both；```
2.在父元素的子元素最后添加一个空的div，并设置```clear：both；```
3.利用css 
```.clearfix{*zoom: 1;}```
```.clearfix:after{content:"";display:block;clear:both}```

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-49b9e2884bebcb79.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后把class名添加到要清楚浮动的父元素上。和第二部相似，只不过用css实现。
4.把父元素设置为BFC:
>float: left | right;
>overflow: hidden | auto | scroll;
>display: table-cell | table-caption | inline-block;
>position: absolute | fixed;


### 3.有几种定位方式，分别是如何实现定位的，参考点是什么，使用场景是什么？
- inherit：从父元素继承；
- static：默认值，元素出现在正常的文档流中。
- relative：相对定位。相对于元素本身的位置进行定位，可以设置top，left，right，bottom进行调整。
*** 使用场景：为绝对定位设置参照物。或者自己本身需要局部调整。

- absolute：绝对定位。相对于static定位以外的第一个祖元素进行定位，一层一层往上找，如果都没有，则相对于HTML进行定位。
*** 使用场景：当想让元素参照特定参照物进行定位时使用。

- fixed：固定定位。相对于浏览器进行定位，无论怎么滚动都会变化位置。
- sticky：对象在常态时遵循普通流。

### 4.z-index 有什么作用? 如何使用?
- z-index：就是网页的z轴，用相对定位绝对定位把两个层重叠在一起。
因为绝对定位的元素脱离了普通流，所以，绝对定位的元素会覆盖在别的元素上面，这是时候可以设置z-index的值来控制堆叠的顺序，设置谁在上面，谁在下边。并且z-index可以设置为负值。

- 关于z-index谁上谁下：
1.如果z-index相同：发生位置重叠，那么按照文档流，后面的覆盖前面的。
2.如果两个元素都设置了z-index：，数值越大，则越靠近观察者。
3.如果一个元素设置了定位，另外一个没有设置，则定位的覆盖未定位的。
4.如果父元素z-index有效，那么子元素无论是否设置了z-index都和父元素一致，会在父元素的上方。
5.如果父元素未定位，子元素定位了，父元素设置了z-index，父元素会失效，子元素会生效。
6.z-index默认值是auto，则不建立层叠的上下文。设置为0，则会建立层叠上下文。

### 5.position:relative和负margin都可以使元素位置发生偏移?二者有什么区别

- position:relative；这个即使设置移动坑还会在。位置还是以前的位置，只不过我们肉眼看到他移动了。
- 负margin：元素的显示位置和在文档流中的位置均发生变化，会影响后面元素在文档流中的位置。

### 6.BFC 是什么？如何生成 BFC？BFC 有什么作用？举例说明
- BFC就是块级格式上下文。浮动、绝对定位（绝对定位、固定定位）元素、块级容器（如inline-block、 table-cell、table-caption）并不是块级盒子，还包括哪些overflow属性值取值visible以外的块级盒子，会为它们的内容物创建一个新的块级格式化上下文。


生成BFC：
>float: left | right;
>overflow: hidden | auto | scroll;
>display: table-cell | table-caption | inline-block;
>position: absolute | fixed;

BFC 有什么作用：
1.可以解决外边框margin重叠问题。
2.可以用来清除浮动，但是多多少少会有缺陷，所以要结合场景来使用。
举个例：

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-950e295ed72eea65.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
你看h1怎么样都撑不开，明明都设置了margin，但只有左右生效。这时候就要让div这个父元素变成BFC，加一点限制。

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-4ee82dc8a4be9227.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

再来个例子：

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-d53c8c2fd4705419.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
父元素的所有子元素都浮动了，父元素就塌陷了，变得无法识别自己的子元素。这时候把父元素变成BFC；

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-5ad894421ffe4a93.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
成功了！！

### 7.在什么场景下会出现外边距合并？如何合并？如何不让相邻元素外边距合并？给个父子外边距合并的范例

- 垂直外边框合并:当两个垂直外边距相遇时，它们将形成一个外边距，较大的优先显示。

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-32d52afbc7fbe70d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
解决办法：让两个元素在不同的BFC中；

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-4efd44c37bc3d0bf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 另外 如果margin为负值：
> .如果两个margin都为负值：哪个值小，显示哪个值，然后从0位置，负向位移。

> .如果正有负的时候：先取出负 margin 中绝对值中最大的，然后，和正 margin 值中最大的 margin 相加。

> .所有在隔壁的margin都要一起参与运算，不能说分布进行。 


- 父子外边距合并
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/8126350-0f02451f8f376a6a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
解决办法，给父元素添加限制，例如```border```，```padding```，```overflow：hidden/auto；``` ```display：inline-block；```
