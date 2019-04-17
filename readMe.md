# 使用app源码编译自己的 小说APP



> 后端管理程序使用的是基于discuz x3.3 UTF-8 编码的一个插件，如果打算使用dz和此插件作为后端管理程序，可去 https://doc.xf512.com/read/jamesonread_app.html  查看
>
> 当然你也可以根据此处提供的接口文件api.php 自行编写，而无需安装dz和插件，只要确保接口名称和返回的数据格式一致即可


###  演示app

![](https://doc.xf512.com/read/images/demo.png)

### 效果图预览(仅供参考)

![](https://doc.xf512.com/read/images/appyulan.jpg)

----

**本页中图片若看不清，请在图片上右键-在新标签页中打开图片**

----

## 零:上传接口文件

> 如果你使用的是本页提供的接口文件，则必须保证已安装dz和相应插件，否则接口文件不可用

解压索取的app源码压缩包，将接口文件夹下的xifeng文件夹，上传到 你安装插件的**网站根目录**下，然后到后台-插件-小说阅读器-手机版-拉到底部，看是否出现了app相关的选项，如果有，则全部填写，不要留空，如果没有，说明你上传的位置不对

此图是discuz x3.3 上的一个小说插件，也是本app所依赖的后台管理程序

![](https://doc.xf512.com/read/images/api12.jpg)

## 一：准备所需的资源
**apicloud studio 软件， 下载地址 http://www.apicloud.com/devtools**

![](https://doc.xf512.com/read/images/xiazai.png)

**下载后,解压到 D 盘 下, 解压后得到一个 APICloud Studio 2 文件夹,双击进入,创建快捷方式**

![](https://doc.xf512.com/read/images/anzhuang1.png)

**双击此快捷方式即可打开此开发工具,后续步骤将要使用这个软件**

![](https://doc.xf512.com/read/images/anzhuang2.png)


**注册 apicloud 帐号,必须注册，注册地址 http://www.apicloud.com/signup**

![](https://doc.xf512.com/read/images/zhuce.png)


## 二：登录www.apicloud.com网站

登录地址为   http://www.apicloud.com/signin   ,用你之前注册的帐号密码登录，登录后 点击 **创建应用** 按钮

![](https://doc.xf512.com/read/images/api1.jpg)

在弹出的对话框中 选择 Native，然后填写app名称(这里的名称只用来在apicloud后台和开发工具软件中显示,**并不是**app安装后在手机显示的)和介绍

![](https://doc.xf512.com/read/images/api2.jpg)

**创建后即自动进入了本app的详细设置页面，开始进行如下设置**

![](https://doc.xf512.com/read/images/api3.jpg)

**创建安卓证书**

![](https://doc.xf512.com/read/images/api4.jpg)

证书信息随意填写

### 添加使用到的模块，下面是用到的模块名称
> smsVerify
>
> fileBrowser
>
> webBrowser
>
> speechRecognizer
>
> FNScanner
>
> audio
>
> UISearchBar
>
> personalCenter
>
> qq
>
> bookReader
>
> fs
>

**点击左侧 模块，然后在右侧再点击模块库，再在搜索框中分别输入如下模块名称搜索，搜索出来了，点击模块的右上角 + 号**

![](https://doc.xf512.com/read/images/api5.jpg)

**复制 id，下面修改config.xml时需要用到**
![](https://doc.xf512.com/read/images/api6.jpg)

## 三：打开 apicloud studio 软件，同步源码

**双击刚才创建到桌面的快捷方式,打开此软件,提示登录,用你注册的apicloud帐号进行登录**

![](https://doc.xf512.com/read/images/denglu1.png)

**登录后的页面效果,点击标签上的叉号关闭这个页面即可**

![](https://doc.xf512.com/read/images/denglu2.png)

### 开始从云端检出你创建的app到本地
**步骤1:工具栏--代码管理--代码检出--Apiclud云端应用**

![](https://doc.xf512.com/read/images/jianchu1.png)
----

**步骤2：点击创建的那个app名字**
![](https://doc.xf512.com/read/images/jianchu2.png)
----

**步骤3：选择检出后的项目存到本地电脑的哪个文件夹下**
![](https://doc.xf512.com/read/images/jianchu3.png)
----

**步骤4:输入HEAD然后回车**
![](https://doc.xf512.com/read/images/jianchu4.png)
----

**步骤5：等待检出成功**
![](https://doc.xf512.com/read/images/jianchu5.png)
----

**解压索取的app源码压缩包，在解压后的源码目录中，复制其中 app源码 目录下的全部文件，然后粘贴到你检出后的项目文件夹中**

![](https://doc.xf512.com/read/images/fugai2.jpg)

如果你忘记了检出的项目所在文件夹，可在左侧项目名称上右键---在资源管理器中显示，如下图（若看不清，请图片上右键-在新标签页中打开图片）
![](https://doc.xf512.com/read/images/app-xiangmu.png)

## 四:在 apicloud studio 软件中开始修改源码
1 . 打开 config.xml文件,将  &lt;widget id="A6936629589063"  中的id使用上面复制的id替换，如图（图片若看不清，请图片上右键在新标签页中打开图片）

![](https://doc.xf512.com/read/images/app-config1.jpg)

同时要修改本config.xml文件中的qq和smsVerify处的信息

![](https://doc.xf512.com/read/images/tianjia1.png)

其中qq、smsVerify 字段中，分别是 QQ登录、手机注册发送验证码所需的appkey和seecret，你需要分别去微信开放平台和QQ开放平台以及mob去申请自己的key。

[QQ的申请地址](http://docs.apicloud.com/Client-API/Open-SDK/qq)

[smsVerify的申请地址](http://docs.apicloud.com/Client-API/Open-SDK/smsVerify)

2 . 打开index.html文件，将里面的 **http://demo.xf512.com/xifeng/** 替换为你的 xifeng 文件夹所在网址，比如 你将接口文件夹 xifeng上传到了 www.abc.com 的根目录下，则这里填写 http://www.abc.com/xifeng/

3 . 打开 book 文件夹下 faxian.html 文件夹， 找到约 70 行左右，将 **demo.xf512.com/** 替换为你的网址，将后面的两处 西风工作室 改成你的网站名称，这里的名称将显示在app发现页面，用户点击后就会打开你填写的网址
![](https://doc.xf512.com/read/images/api15.jpg)

## 五:在 apicloud studio 软件中提交代码到apicloud平台

**修改完成后按下图所示进行代码提交**

步骤1：项目名称上右键  --Git--Git add+commit

![](https://doc.xf512.com/read/images/tijiao1.png)

----
然后在方法随便输入文字后按ctrl+s

![](https://doc.xf512.com/read/images/tijiao2.png)

----

步骤3：同步代码到apicloud云端，工具栏--代码管理--同步到云端，然后等待提示成功

![](https://doc.xf512.com/read/images/tijiao3.png)

----

等待提交完成
![](https://doc.xf512.com/read/images/tijiao4.png)

## 六:在 apicloud studio 软件中编译app

这就是最后一步了，提交同步完成后，在软件左侧 项目名称上右键-云编译

![](https://doc.xf512.com/read/images/api17.jpg)

**点击左侧云编译，右侧填写应用名称、选中android平台、选择正式版，然后点击底部的 云编译 按钮**

![](https://doc.xf512.com/read/images/api18.jpg)

**等待编译结束，然后点击下载你的安装包就可以了**

将下载后apk安装包重命名为 版本编号.apk（如 0.9.85.apk），然后上传到你网站上接口文件夹 xifeng目录下，并在插件后台-手机版-APP下载地址 中填写这个apk安装包的网址，这样在app中可以检测新版本


> 比如这个app编译时的版本 显示为 0·9·84，则将下载后的apk安装包重命名为 0.9.84.apk，然后上传到xifeng文件夹下，并在插件后台-手机版-APP下载地址 中填写这个apk安装包的网站  http://demo.xf512.com/xifeng/0.9.85.apk


![](https://doc.xf512.com/read/images/api-rename.jpg)

![](https://doc.xf512.com/read/images/api19.jpg)

![](https://doc.xf512.com/read/images/api20.jpg)
