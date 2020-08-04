---
title: 主题使用文档
date: 2020-08-03 21:41:42
categories:
- 文档
excerpt: 主题使用文档
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

{% note %}
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
### lazyload

在主题配置选项`lazyload`中设置`enable: true`开启懒加载（默认开启）

`loadingImg`中可以设置加载图，可以在post中设置`banner_img_set`进行覆盖实现缩略图效果

### 主题颜色

本主题中大部分颜色都可以在主题配置选项`color`中进行配置

### 字号与字体

在主题配置选项`font`中可以设置`font-size`和`font-family`

### 静态资源

主题大部分第三方资源索引都可以在主题配置选项`cdn`中进行配置，可以自定义其他资源路径

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
### 社交连接

在主题配置中

```yaml
# about page config
  about:
    description: description
    social_links:
    	- { icon: icon, link: your_links }
    	- ...more
```

