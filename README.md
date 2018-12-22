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
| .Site.Taxonomies   | 网站作者       |String |
| .Site.Title   | 网站作者       |String |
| .Site.BuildDrafts   | 网站作者       |String |
| .Site.Copyright   | 网站作者       |String |
| .Site.Data   | 网站作者       |String |
| .Site.DisqusShortname   | 网站作者       |String |
| .Site.Files   | 网站作者       |String |
| .Site.GoogleAnalytics  | 网站作者       |String |
| .Site.Home   | 网站作者       |String |
| .Site.IsMultiLingual  | 网站作者       |String |
| .Site.IsServer  | 网站作者       |String |
| .Site.Language.Lang  | 网站作者       |String |
| .Site.Language.LanguageName  | 网站作者       |String |
| .Site.Language.Weight  | 网站作者       |String |
| .Site.Language  | 网站作者       |String |
| .Site.LanguageCode  | 网站作者       |String |
| .Site.LanguagePrefix  | 网站作者       |String |
| .Site.Languages  | 网站作者       |String |
| .Site.LastChange  | 网站作者       |String |
| .Site.Menus  | 网站作者       |String |
| .Site.Pages  | 网站作者       |String |
| .Site.Permalinks  | 网站作者       |String |
| .Site.RegularPages  | 网站作者       |String |
| .Site.RSSLink  | 网站作者       |String |
| .Site.Sections  | 网站作者       |String |


### .Site.Params/[Pramas] 的使用。