### 随机数题目

#### 1.写一个函数，返回从min到max之间的 随机整数，包括min不包括max
~~~
function random(min,max){
 return Math.floor(Math.random()*(max-min))+min
}
~~~

#### 2.写一个函数，返回从min到max之间的 随机整数，包括min包括max
~~~
function random(min,max){
 return Math.floor(Math.random()*(max+1-min))+min
}
~~~

#### 3.写一个函数，生成一个长度为 n 的随机字符串，字符串字符的取值范围包括0到9，a到 z，A到Z。
~~~
function getRandStr(len){
    var dict="0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
    var wrap=""
    for(var i=0; i<len; i++){
        wrap+=dict[Math.floor(Math.random()*62)]
    }
    console.log(wrap)
}
var str = getRandStr(10);
~~~

#### 4.写一个函数，生成一个随机 IP 地址，一个合法的 IP 地址为 0.0.0.0~255.255.255.255
~~~
function random(a,b){
    return Math.floor(Math.random()*(b-a))+a
}
function randomIp(){
    var wrap=[];
    for(var i=0; i<4; i++){
        wrap.push(random(0,256))
    }
    console.log(wrap.join("."))
}
randomIp()
~~~

#### 5.写一个函数，生成一个随机颜色字符串，合法的颜色为#000000~ #ffffff
~~~
unction random(a,b){
    return Math.floor(Math.random()*(b-a))+a
}
function randomColor(){
    var color="0123456789abcdef"
    var wrap=""
    for(var i=0; i<6; i++){
        wrap+=color[random(0,16)]
    }
    console.log("#"+wrap)
}
randomColor()
~~~

### 数组题目

#### 1.写一个函数，操作数组，数组中的每一项变为原来的平方，在原数组上操作
~~~
function squareArr(arr){
    for(var i=0;i<arr.length;i++){
        arr[i] = Math.pow(arr[i], 2);
    }
    console.log(arr)
}
var arr = [2, 4, 6]
squareArr(arr)
console.log(arr)// [4, 16, 36]
~~~

#### 2.写一个函数，操作数组，返回一个新数组，新数组中只包含正数，原数组不变
~~~
function filterPositive(arr){
    var warp=[];
    for(var i=0; i<arr.length; i++){
        if (arr[i]>0 && typeof arr[i]==="number" ) {
             warp.push(arr[i])
        }
    }
    return warp
}
var arr = [3, -1,  2,  '饥人谷', true]
var newArr = filterPositive(arr)
console.log(newArr) //[3, 2]
console.log(arr) //[3, -1,  2,  '饥人谷', true]
~~~

### date题目
#### 1.写一个函数getChIntv，获取从当前时间到指定日期的间隔时间
~~~
function getChIntv(target){
    var targetTime=new Date(target);
    var todayTime=new Date();
    var timeReduce=Math.abs(targetTime-todayTime);

    var totalmill=Math.floor(timeReduce/1000)
    var mill=totalmill%60;

    var totalMinutes=Math.floor(timeReduce/1000/60)
    var minutes=totalMinutes%60

    var totalhours=Math.floor(timeReduce/1000/60/24)
    var hours=totalhours%24

    var totalDays = Math.floor(timeReduce/1000/60/60/24);
    return "距离除夕还有"+totalDays + "天" + hours + "时" + minutes +"分" + mill+"秒"
}
var str = getChIntv("2017-02-08");
console.log(str);  
~~~
#### 2.把hh-mm-dd格式数字日期改成中文日期
~~~
function getChsDate(arr){
var str = arr.split('-'); 
var str1=['零','一','二','三','四','五','六','七','八','九','十','十一','十二','十三','十四','十五','十六','十七','十八','十九','二十','二十一','二十二','二十三','二十四','二十五','二十六','二十七','二十八','二十九','三十','三十一']
var month=str1[parseInt(str[1])]
var day=str1[parseInt(str[2])]
var year=""
for(var i = 0; i < str[0].length; i++){
    year+=str1[str[0][i]]
}

    return year + "年" + month + "月" + day + "日"
}
var str = getChsDate('2015-01-08');
console.log(str);  // 二零一五年一月八日
~~~

#### 3.写一个函数，参数为时间对象毫秒数的字符串格式，返回值为字符串。假设参数为时间对象毫秒数t，根据t的时间分别返回如下字符串:

刚刚（ t 距当前时间不到1分钟时间间隔）
3分钟前 (t距当前时间大于等于1分钟，小于1小时)
8小时前 (t 距离当前时间大于等于1小时，小于24小时)
3天前 (t 距离当前时间大于等于24小时，小于30天)
2个月前 (t 距离当前时间大于等于30天小于12个月)
8年前 (t 距离当前时间大于等于12个月)
~~~
function friendlyDate(time){
    var nowTime=new Date()
    //var taiget=new Date(time)
    var sec=nowTime-time
    var mill=Math.floor(sec/1000)
    var str=""
    if (mill<60) {
        str="刚刚"
    }else if(mill>180 && mill<3600){
        str="3分钟前"
    }else if(mill>=3600 && mill<86400){
        str="8小时前"
    }else if (mill>=86400 && mill<2592000) {
        str="3天前"
    }else if(mill>=2592000 && mill<31536000){
        str="2月前"
    }else{
        str="8年前"
    }
    return str
}
var str = friendlyDate( '1484286699422' ) //  1分钟前
var str2 = friendlyDate('1483941245793')
console.log(str)
console.log(str2)
~~~
