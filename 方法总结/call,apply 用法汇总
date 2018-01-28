### this && arguments
~~~
function fn() {
  console.log(this)
  console.log(arguments)
}
fn() //window //[]
//一般情况下 如果this 没有指定对象，那么就会指向全局 window
//arguments 是代表实参，如果没有参数的传递 默认值就是一个伪数组
~~~
### call 
- this 为什么必须是对象
因为 this 就是函数与对象之间的羁绊
~~~
var person = {
          name: 'frank',
          sayHi: function(person){
              console.log('Hi, I am' + person.name)
          },
          sayBye: function(person){
              console.log('Bye, I am' + person.name)
          },
          say: function(person, word){
              console.log(word + ', I am' + person.name)
          }
      }
~~~
- 看上面代码 我们通常会把person.name 改写成 this.name
- 但是如果JS里面 没有this 我们就只可以写成person.name，就像上面一样，这样写有一个好处，令阅读者更加清晰知道，你要打印出哪个name。
- 这样说，我们写代码就完成可以不用this。
~~~
//如果用this 我们会这样打印
person.sayHi()
person.sayBay()
person.say('你好')
//可是这样源码就要改变
var person = {
          name: 'frank',
          sayHi: function(){
              console.log('Hi, I am' + this.name)
          },
          sayBye: function(){
              console.log('Bye, I am' + this.name)
          },
          say: function(word){
              console.log(word + ', I am' + this.name)
          }
      }

//如果不用this 我们可以这样打印
person.sayHi(person)
person.say(person)
person.say(person,'你好')

//同样 我们可以用call 更清晰的打印
person.sayHi.call(person)
person.sayBay.call(person)
person.say.call(person,'你好')
~~~
***this 是call 的第一个参数 所以 我们在调用的时候 才能知道this 指向谁,所以this其实很不靠谱***

- 我们还会经常疑惑的一种写法
~~~
 var fn = person.sayHi
 person.sayHi() // this === person
 fn()  // this === window
~~~

### call 和 apply 的区别
~~~
function fn(){
  var n = 0
  for(var i = 0; i<arguments.length; i++){
    n += arguments[i]
  }
  return n
}
//如果给出的参数是一个数组 而我们想数组的值相加
//用call 就会有点鸡肋
var a = [1,2,3,4,5]
fn.call(null,a[0],a[1]....) //傻逼才会这样做

//这时候我们就用apply
fn.apply(null,a) //applay的第二参数是一个数组
~~~

- 本文只做一个总结 如果你对this 很清楚 那么继续用this
- 如果你觉用call 和 apply 会令人更清晰 是时候改变了
