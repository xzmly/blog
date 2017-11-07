### 教你如何安装win10下的子系统linux到配置node最新版本
***
#### 开启windows10的子系统 
- 第一步
![123.png](http://upload-images.jianshu.io/upload_images/8126350-1a9be80d8909c918.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




- 第二步
![456.png](http://upload-images.jianshu.io/upload_images/8126350-cf2c5a9b51f4ab07.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 第三部
右键你开始按钮，看到windows Powershell(管理员)，打开输入
~~~
bash
# 或
lxrun /install /y
~~~

等待安装
(中间会叫你创建user和password)

- 第四步
重启电脑，等待更新

- 第五步
下载终端神器conemu(这里自己谷歌一下,或者联系我)

- 第六步
根据[这个网址](http://blog.csdn.net/M1mory/article/details/72591289). 里的内容配置好conemu


- 第七步 
这时候打开你配置好的conemu,输入bash,就能进入子系统了
- ps:这里给一个温情提示，最好先获取root权限
输入:
~~~
sudo passwd root
~~~
- 以后你想进入管理员模式 只要su,然后输入密码就行了


- 这是右键打开终端命令
~~~
sudo apt-get install nautilus-open-terminal
~~~

#### 安装nvm
- 这里你理解成你要为你新系统下载迅雷
- 第一步
再conemu里输入bash，进入到linux
输入
~~~
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash


nvm install stable


nvm use stable
//上面是安装nvm


//下面是安装node和npm,并且是node最新版本
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs


sudo ln -s $(which node) /usr/bin/node


sudo ln -s $(which npm) /usr/bin/npm
~~~

依次执行以上命令，不要问为什么。

#### 查看node和npm版本
输入
~~~
node -v

npm -v
~~~

完成了~~~！！！
