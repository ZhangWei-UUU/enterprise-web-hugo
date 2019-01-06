+++
title = "MacOS 安装Flutter"
date = "2015-10-10T13:07:31+02:00"
tags = ["ipsum"]
categories = ["lorem"]
banner = "img/banners/flutter.png"
+++

在官网上[下载](https://flutter.io/docs/get-started/install/macos)zip最新安装包,

解压在某个文件夹位置，然后在该文件夹下运行如下命令（注：不是进入flutter文件夹）：

```
export PATH=$PATH:`pwd`/flutter/bin
```

之后检查本机开发环境中缺少那些插件：
```
flutter doctor
```
<!--more--> 
  