---
title: 公式渲染
date: 2020-07-27 21:06:41
tags:
- mathjax
- katex
- 数学公式
categories:
- 文档
excerpt: 数学公式演示
banner_img: https://img.songhn.com/img/code.jpg?imageslim
banner_img_set: https://img.songhn.com/img/code.jpg?imageMogr2/blur/1x0/quality/1
---
## 简介

### 启用公式

本主题支持 `mathjax` 和 `katex` 两大渲染引擎，您可以在博客主题设置 `latex` 中  `enable: true` 启用。

### 更换渲染器

由于Hexo本身渲染器的冲突，有一部分公式无法渲染，建议采用其他渲染器，首先
```
npm uninstall hexo-renderer-marked -S
```
之后`mathjax`推荐`hexo-renderer-kramed`，`katex`推荐`hexo-renderer-markdown-it-plus`
```
npm install hexo-renderer-kramed -S
npm install hexo-renderer-markdown-it-plus -S
```
{% note warning %}
注意，您只可以保留一个渲染器
{% endnote %}

## 演示

以下所有公式均通过 `katex` 渲染

### 整行公式

$$f(a) = \frac{1}{2\pi i} \oint\frac{f(z)}{z-a}dz$$


$$\cos(\theta+\phi)=\cos(\theta)\cos(\phi)−\sin(\theta)\sin(\phi)$$

$$\int_D ({\nabla\cdot} F)dV=\int_{\partial D} F\cdot ndS$$

$$\vec{\nabla} \times \vec{F} =\left( \frac{\partial F_z}{\partial y} - \frac{\partial F_y}{\partial z} \right) \mathbf{i}+ \left( \frac{\partial F_x}{\partial z} - \frac{\partial F_z}{\partial x} \right) \mathbf{j}+ \left( \frac{\partial F_y}{\partial x} - \frac{\partial F_x}{\partial y} \right) \mathbf{k}$$

$$\sigma = \sqrt{ \frac{1}{N} \sum_{i=1}^N (x_i -\mu)^2}$$

$$(\nabla_X Y)^k = X^i (\nabla_i Y)^k =X^i \left( \frac{\partial Y^k}{\partial x^i} + \Gamma_{im}^k Y^m \right)$$

$$
det(J_G) =\frac{\partial{x_{d+1}}}{\partial{z_{d+1}}}\frac{\partial{x_{d+2}}}{\partial{z_{d+2}}}...\frac{\partial{x_D}}{\partial{z_D}} \\
=β_{d+1}β_{d+2}...β_{D}
$$
### 行内公式

求根公式是$x = {-b \pm \sqrt{b^2-4ac} \over 2a}$

$E=mc^2$是质能方程式

对于一个序列$a_1,a_2,\cdots,a_m$，有$a_1+a_2+\cdots+a_m=2\cdot(a_1\oplus a_2\oplus\cdots\oplus a_m)$