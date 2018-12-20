# enterprise-web-hugo
A enterprise web template, which build on hugo

### 导航设置

在导航设置中，`[menu]`属性负责管理`[[menu.main]]` 可以无限添加导航，但是由于识别符的原因，如果没有具体的路由页面，没有的路由会直接跳入404. 而这个识别符它所导向的地方就`content`文件夹中的`.md`文件.    

### 架构解释

- layouts
  * _default
    * list.html
    * single.html // 某个博客内部页面
  * page
    * single.html // 页面的主要HTML壳。


### 参数配置

#### md参数设置

```
+++
title = "页面标题"
id="页面ID"
description = "页面文本描述"
keywords = ["关键字"]
+++
```

在`content/xx.md` 关键的参数是`id`，这个参数的设置与否决定了当前页面使用的是使用默认的`single.html`还是与其id对应的自定义模板。

