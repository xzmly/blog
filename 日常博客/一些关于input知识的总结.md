
### form表单有什么作用
> - 用于声明表单，收集规定范围数据，也就是```<form>```和```</form>```里面包含的数据将被提交到服务器或者电子邮件里。

### form的常用属性
>- ```<form action="要去的地方" method="get/post">```
> - get代表你发送的数据会在链接上看到，安全很差
> - post发送数据在链接上不能看见，隐藏了

### 有哪些常用的input 标签，分别有什么作用？
|标签|作用|
-|-
|```<input type="text">```|单行文本框|
|```<input type="password">```|密码框|
|```<input type="checkbox">```|复选框 （注意name要设置相同 ）|
|```<input type="radio">```|单行文本框 （注意name）要设置相同|
|```<input type="file">```|上床文件|
|```<input type="submit">```|提交按钮|
|```<input type="bottom ">```|普通按钮|
|```<input type="reset ">```|重置按钮|
|```<textarea name="ar" id="" cols="30" rows="10"></textarea>```|一个文本框 可以设置宽高|
|```<select name="" id=""> <option value=""></option></select>```|下拉框，输出的是option的value值|

### 在input里，name 有什么作用？
> - 提交时候数据的名字

### radio 如何 分组?
> - 男```<input type="radio" name="tropism" value="男">```
> - 女```<input type="radio" name="tropism" value="女">```
(这里记住name要设置相同)

### placeholder 属性有什么作用?
> - 例如text会在里面设置文字，当获得焦点时候就会被删除

### type=hidden隐藏域有什么作用? 举例说明
 > - 隐藏域在页面中,用户是不可见的，在表单中插入隐藏域的目的在于收集或发送信息，以利于被处理表单的程序所使用。浏览者单击发送按钮发送表单的时候，隐藏域的信息也被一起发送到服务器，从后台给用户隐藏域中value添加值，就可以识别用户，提高安全性。
