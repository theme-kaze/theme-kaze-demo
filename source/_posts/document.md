---
title: 主题使用文档
date: 2020-08-03 21:41:42
categories:
- 文档
excerpt: 主题使用文档
banner_img: https://img.songhn.com/img/gallery.png?imageslim
banner_img_set: https://img.songhn.com/img/gallery.png?imageMogr2/blur/1x0/quality/1
---

## 主题简介

Kaze是基于Hexo博客引擎的响应式主题，由[theme-kaze](https://github.com/theme-kaze)开发维护

## 使用须知

文档并不包含所有配置项，其他选项请参考主题配置和[Hexo文档](https://hexo.io/)，如有配置上的其他疑问可以在issue中提出

## 安装主题

### 直接通过npm/yarn安装

在Hexo5.0及以上版本中您可以直接通过输入

```bash
npm install hexo-theme-kaze
```

直接安装主题

### 其他方式

如果您有其他需要可以在`your site/themes`下输入

```bash
git clone https://github.com/theme-kaze/hexo-theme-Kaze.git
```

或者下载主题压缩包在`your site/themes`下解压，并且将`hexo-theme-Kaze`重命名为`Kaze`

{% note primary %}
重命名为`Kaze`是为了与通过`npm/yarn`下载保持一致性
{% endnote %}

## 持续升级

在Hexo5.0及以上版本中您可以在站点根目录中新建`_config.Kaze.yml`进行自定义配置，具体优先级参见相关文档

在Hexo其他版本中您可以在站点目录`source`文件中新建`kaze_config.yml`进行自定义配置，`kaze-config.yml`设置优先于主题配置设置

之后直接采取`git pull`或覆盖主题目录等方式便可直接升级无需替换配置

{% note warning %}
请关注Release中的Breaking Changes会提示对配置造成不下兼容的改动 请自行更改
{% endnote %}

## 总体
### 懒加载

在主题配置选项`lazyload`中设置`enable: true`开启懒加载（默认开启）

`loadingImg`中可以设置加载图，可以在post中设置`banner_img_set`进行覆盖实现缩略图效果

### 文件压缩

主题自带文件压缩，可以配合GZIP或其他优化手段提高网页访问速度，默认关闭，可以在

```yaml
minify:
  enable: false
  css: true
  js: true
  html: true
```

中进行配置

{% note warning %}
需要注意开启压缩后会影响`hexo g`的性能
{% endnote %}

### 主题颜色

本主题中大部分颜色都可以在主题配置选项`color`中进行配置

### 字号与字体

在主题配置选项`font`中可以设置`font-size`和`font-family`

### 静态资源

主题大部分第三方资源索引都可以在主题配置选项`cdn`中进行配置，可以自定义其他资源路径

### 动画

在主题配置文件中`animation config`调整主题动画效果，目前仅支持控制回到顶部动画的开关

###  图标

主题图标依赖于[iconfont](https://www.iconfont.cn/)，内置了一部分社交图标，您可以自定义其他icon文件或者解决方案来添加自定义图标

<img src="https://img.songhn.com/img/iconfont.png?imageslim">

## 首页

### 文章头图

在文章`Front-matter`中`banner_img`可以设置首页头图

## 关于

关于页面需要自行创建，在站点`source`中新建`about`文件夹并在文件夹内创建`index.md`，该文件至少需要包含

```yaml
# at ${yoursite}/about/index.md
---
title: 关于
layout: about
---
```
### 社交链接

在主题配置中

```yaml
# about page config
about:
  description: description
social_links:
  - { icon: icon, link: your_links }
  - ...more
```

在主题配置文件中按如上格式填写`social_links`即可创建社交链接，`icon`相关可以参见[图标](#图标)

## 友链

友链格式按如下填写即可生成友链页面

```yaml
links:
  example-name-1: 
    url: https://example.com
    avatar: https://example.com/avatar.jpg
  example-name-2: 
    url: https://example.com
    avatar: https://example.com/avatar.jpg
```

## 文章页

### 目录

主题目录通过Hexo原生函数生成，具体可参见[文档](https://hexo.io/docs/helpers#toc)

```yaml
toc:
  showListNumber: false
  maxDepth: 6
  minDepth: 1
```

`showListNumber`: 是否生成编号

`maxDepth`: TOC最大深度

`minDepth`: TOC最小深度

### 代码高亮

参见代码[高亮文档](https://demo.theme-kaze.top/highlight/)

### 数学公式

主题支持`mathjax`和`katex`两种渲染引擎，具体参见[相关文档](https://demo.theme-kaze.top/latex/)

### Front-matter

#### banner_img

设置文章与首页头图

#### banner_img_set

在图片加载时预先加载的图片，可以设置为loading图或缩略图等

#### excerpt

为文章设置在首页显示的简介，还可以通过`<!--more-->`来控制显示

### 评论

支持`valine`，`gitalk`和`livere`

具体设置可参考主题配置文档说明和相关评论插件文档

### 字数统计

主题集成[hexo-wordcount](https://github.com/willin/hexo-wordcount)插件，在主题配置文件中设置

```yaml
wordcount:
  enable: true
```

开启（默认开启）

### 图片画廊

图片画廊功能基于[fslightbox](https://fslightbox.com/)，在主题配置文件中设置

```yaml
fslightbox:
  enable: true
```

开启（默认开启）

### 标签插件

主题集成了一些标签方便书写

#### note

在`markdown`文件中如下书写即可

```markdown
{% note style %}
...markdown content
{% endnote %}
```

有五种样式可以选择，`primary`，`success`，`info`，`warning`，`danger`

{% note primary %}
primary
{% endnote %}

{% note success %}
success
{% endnote %}

{% note info %}
info
{% endnote %}

{% note warning %}
warning
{% endnote %}

{% note danger %}
danger
{% endnote %}

### 备案信息

您可以在主题配置文件内增加您的备案信息。

```yaml
footer:
  #------------------------
  # 备案配置
  # 请将公安备案的缩略图置于 ${yoursite}/img/beian.png
  RecordInfo: "" # '某ICP备xxx号'
  govRecordInfo: "" # '某公网安备xxx号'
  govRecordUrl: "" # 公网安备案信息地址
  #------------------------
```