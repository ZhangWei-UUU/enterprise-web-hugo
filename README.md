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
