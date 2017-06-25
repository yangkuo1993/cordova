# cordova

最近接手一个cordova混合app的开发任务，启动过程中出现问题较多，所以想写一个配置过程，希望能帮助到其他人。

分为两个配置版本，windows、mac.想要测试ios手机需要安装xcode，android手机需要安装android studio。

首先是需要安装nodejs，https://nodejs.org/en/ 这里是官网安装，不过更推荐nvm（nodejs版本管理工具）安装，这样根据不同的需要，可以随时切换nodejs版本。

安装好nodejs之后，进行cordova安装

在终端执行npm install -g cordova 命令全局安装cordova ,mac系统执行sudo npm install -g cordova

在终端执行cordova -v 查看cordova是否执行成功（安装成功后的cordova版本）

调试android程序需要安装Android studio，与java。并进行环境变量配置，此处略过安装教程。

以上环境安装成功后

执行cordova create demoOne com.example.demoOne 来进行cordova项目的创建。
执行cd demoOne进入cordova项目
执行cordova platform add android 或 cordova platform add ios 进行android与ios平台的添加，这一步基本不会报错（环境安装好的情况下）
如图：

![Image text](https://github.com/yangkuo1993/cordova/blob/master/img/WechatIMG1.jpeg)



执行cordova build android 进行项目构建，这一步出错的几率较大，我基本上是卡在这一步了。构建的时候缺少gradle，需要进行安装，建议用android studio打开项目下，platforms文件夹下android文件夹，会自动进行gradle安装，大部分原因都是卡在gradle上了，因为进行在线下载，很慢。如果要进行本地配置，请自行解决。安装完成之后会看见项目文件打开。紧接着执行cordova build android，构建成功后执行cordova run android（在设备上安装成功，并打开）。ios版本同样执行cordova build ios后执行cordova run ios，会运行项目。

顺序执行：如下图
![Image text](https://github.com/yangkuo1993/cordova/blob/master/img/WechatIMG4.jpeg)
![Image text](https://github.com/yangkuo1993/cordova/blob/master/img/WechatIMG6.jpeg)
![Image text](https://github.com/yangkuo1993/cordova/blob/master/img/WechatIMG7.jpeg)
