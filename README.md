![](https://img.shields.io/github/stars/itgoyo/Mac-OBS-DanMu-DianGe.svg?style=social&label=Star)

项目地址:https://github.com/itgoyo/Mac-OBS-DanMu-DianGe

源项目地址: https://github.com/Clunt/livetool

简介：Mac版本的OBS很多动能都没有，不像在Windows下面有小葫芦直播工具，简单无脑的就可以往里面添加插件，连弹幕显示，点歌功能都没有。自己在无聊的时候看到一位朋友@[Clunt](https://github.com/Clunt/livetool)在斗鱼直播敲代码，然后觉得他做的页面挺好看的，然后一问是他自己做的一个框架，支持`弹幕提醒`还有`弹幕点歌`。中间有什么不懂的都问他，他都一一解答了。


   * [步骤：](#步骤)
   * [需要打开的三个网页分别如下](#需要打开的三个网页分别如下)
   * [本人使用框架所遇到的问题以及解决方式:](#本人使用框架所遇到的问题以及解决方式)

# 步骤：  
- 安装node.js
- 下完Github项目文件
- Chrome安装项目文件中的extension插件

使用终端进入到项目文件然后使用命令`node ./bin/www`出现一下内容就表示成功，其中`201001`是我自己的房间号，需要自己修改根目录下面的`config.js`文件，改成自己的房间号。
```
务器已运行，端口： 6688
登陆: 201001
登陆成功: 201001
加入全局分组
```
为了方便测试是否已经搭建成功，最好先用此时此刻在播的人气比较多的房间，因为里面弹幕多方便测试。还有很多主播的房间号都改成了自己的id，这时候怎么获取到他的房间号呢，直接点击举报，在举报项目页面会有主播相应的房间号码。

# 需要打开的三个网页分别如下

直播工具管理终端:http://127.0.0.1:6688/#admin?core

直播工具显示页面:http://127.0.0.1:6688

网易云在线点歌页面:http://music.163.com/?livetool#/search/

点歌命令
```
#点歌 歌名@歌手#
#切歌#
```

# 本人使用框架所遇到的问题以及解决方式:

>`Error: Cannot find module 'express'`

解决办法:`npm install express`

>`Error: Cannot find module '../config'`

解决办法:`cp doc/config.js config.js`也就是把`doc`目录下面的`config.js`复制到根目录

>点歌页面已经有歌曲的名称但是没有在网易云网页版播放

解决办法: Chrome安装项目文件中的`extension`插件，不会安装的自行百度

-----
备注：

1.想要使用麦克风的话，就在OBS属性里soundflower 64ch

2.打开`Audio Hijack`然后打开麦克风输入

3.在右上角喇叭部分选择多设备输出，这样子才有声音

### Linux版本注意
由于原本官方没有提供自带的浏览器插件，所以在Linux也想使用这个环境的话需要安装一个OBS的插件地址https://github.com/bazukas/obs-linuxbrowser
- mkdir -p $HOME/.config/obs-studio/plugins
- tar xfvz linuxbrowser0.3.1-obs20.0.1-64bit.tgz -C $HOME/.config/obs-studio/plugins/
- Install the dependencies: libgconf-2-4 (sudo apt-get install libgconf-2-4 in Ubuntu)
