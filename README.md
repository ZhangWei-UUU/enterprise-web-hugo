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

## Hugo 的变量世界

### Site 变量

Site变量是Hugo框架中的全局变量，其中的大部分的变量是在配置文件中声明定义。
他们在配置文件中的语法格式和模板文件中的格式有所不同,在配置文件中不允许有大写字母：

```toml
title:"Hugo Demo tutorial"
author:"Zhang Wei"
```

```html
<h1>{{.Site.Title}}</h1>
<i>{{.Site.Author}}</i>
```

Site 变量查询列表

| 变量名称  | 解释       |   形式  |
| :----:  |  :----:    |  :----:|
| .Site.AllPages |    所有的页面       |   Array      |
| .Site.BaseURL  |    当前网站的基础url，一般为`/`   |   String      |
| .Site.Author   | 网站作者       |String |
| .Site.Taxonomies   | 网站逻辑，是Hugo的重要特性 |String |
| .Site.Title   | 网站标题      |String |
| .Site.BuildDrafts   | 默认情况值为false, 网站是否安装配置文件生成草稿     | boolean |
| .Site.Copyright   | 网站Copyright   |String |
| .Site.Data   | 自定义网站数据      |String |
| .Site.DisqusShortname   | 网站作者       |String |
| .Site.Files   | 网站所有的资源文件  |String |
| .Site.GoogleAnalytics  | 使用GoogleAnalytics对网站进行追踪数据分析 |String |
| .Site.Home   | 主页设置，在hugo中主页的设置不同于其他页面      |String |
| .Site.IsMultiLingual  | 当前网站是否为多语言网站  | boolean |
| .Site.IsServer  | 表示当前网站是否使用自带的hugo server  | boolean |
| .Site.Language.Lang  | 网站作者       |String |
| .Site.Language.LanguageName  | 语言名称：如English,Chinese    |String |
| .Site.Language.Weight  | 语言序列       |String |
| .Site.Language  | 当前使用语言       |String |
| .Site.LanguageCode  | 语言代码，用于配置文件      |String |
| .Site.LanguagePrefix  |用于语言切换设置前缀  |String |
| .Site.Languages  | 网站作者       |String |
| .Site.LastChange  |       |String |
| .Site.Menus  | 网站主菜单    |String |
| .Site.Pages  | 以时期进行排序，最新的日期页面排在第一位 | Array |
| .Site.Permalinks  | 网站链接路由设置       |String |
| .Site.RegularPages  |        |String |
| .Site.RSSLink  |       |String |
| .Site.Sections  | 网站顶级文件夹 |String |


### .Site.Params/[Pramas] 的使用。