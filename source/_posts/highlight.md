---
title: 代码高亮
date: 2020-08-03 14:47:49
tags:
- 代码高亮
categories:
- 文档
excerpt: 代码高亮文档与演示
banner_img: https://img.songhn.com/img/latex.jpg?imageslim
banner_img_set: https://img.songhn.com/img/latex.jpg?imageMogr2/blur/1x0/quality/1
---
## 简介

<link rel="preload" href="/js/lib/prism/prism.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-coy.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-dark.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-funky.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-okaidia.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-solarizedlight.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-tomorrow.min.css" as="style">
<link rel="preload" href="/js/lib/prism/prism-twilight.min.css" as="style">

### 高亮方案

本主题没有使用自定义高亮方式，高亮方案在Hexo本身支持的 `highlightjs` 和 `prismjs` 基础上修改得到

### 使用highlightjs

```yaml
highlight:
  enable: true
  line_number: false
  auto_detect: false
  tab_replace: ''
  wrap: true
  hljs: true
prismjs:
  enable: false
  ...
```

{% note warning %}
`highlight` 和 `prismjs` 的 `enable: true` 只能保留一个
{% endnote %}

在站点配置文件将 `highlight` 设置 `enable: true` 即可开启，`line_number` 选项本主题暂不支持显示

若需要支持代码高亮可设置 `hljs: true`，该配色方案参考了 `tomorrow night` 等配色主题

其他具体参数设置可参考 [Hexo相关文档 ](https://hexo.io/docs/syntax-highlight)

## 使用prismjs

在 `prismjs` 中设置 `enable: true` 和 `preprocess: true` 即可开启 默认支持 `Line Numbers` 和 `Show Languages` 两个插件 如果需要其他插件支持可以设置 `preprocess: false`

{% note warning %}
当前主题版本不支持 `preprocess: false` 自动引入相关文件 如有相关需求请自行引入相关 css 与 js 文件
{% endnote %}

设置 `line_number: true` 即可显示行号

## 演示

以下演示采用 `prism`，`highlight` 在主题效果可参见（TODO）

有八种高亮主题可选择

<button class="postbutton" style="color: #fff;">default</button> <button class="postbutton" style="color: #fff;">coy</button> <button class="postbutton" style="color: #fff;">dark</button> <button class="postbutton" style="color: #fff;">funky</button> <button class="postbutton" style="color: #fff;">okaidia</button> <button class="postbutton" style="color: #fff;">solarizedlight</button> <button class="postbutton" style="color: #fff;">tomorrow</button> <button class="postbutton" style="color: #fff;">twilight</button>


### Javascript

```js
const smoothScrollToTop = () => {
  let yTopValve = (window.pageYOffset || document.body.scrollTop || document.documentElement.scrollTop);
  if (yTopValve > 1) {
    window.requestAnimationFrame(smoothScrollToTop);
    scrollTo(0, Math.floor(yTopValve * 0.85));
  } else {
    scrollTo(0, 0);
  }
};

setTimeout(() => {
  document.getElementById('scrollbutton').onclick = smoothScrollToTop;
}, 0);
```

### C++

```cpp
#include<cstdio>
#include<iostream>
#include<algorithm>
const int maxn=1050;
const int maxm=20000010;
int h,n,v[maxn],w[maxn],f[maxm],maxx;
int main()
{
	cin>>h>>n;
	memset(f,0x3f,sizeof(f));
	f[0]=0;
	for(int i=1;i<=n;i++) cin>>v[i]>>w[i],maxx=max(v[i],maxx);
	for(int i=1;i<=n;i++)
	{
		for(int j=v[i];j<=h+maxx;j++)
			f[j]=min(f[j],f[j-v[i]]+w[i]);	
	}
	int ans=inf;
	for(int i=h;i<=h+maxx;i++) ans=min(ans,f[i]);
	cout<<ans<<endl;
	return 0;
}
```

### PHP

```php
<?php
error_reporting(0);
if(!isset($_GET['num'])){
    show_source(__FILE__);
}else{
        $str = $_GET['num'];
        $blacklist = [' ', '\t', '\r', '\n','\'', '"', '`', '\[', '\]','\$','\\','\^'];
        foreach ($blacklist as $blackitem) {
                if (preg_match('/' . $blackitem . '/m', $str)) {
                        die("what are you want to do?");
                }
        }
        eval('echo '.$str.';');
}
?>
```



### JSON

```json
{
  "name": "hexo-theme-kaze",
  "description": "hexo-theme-kaze",
  "author": "theme-kaze",
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/theme-kaze/hexo-theme-Kaze/issues"
  },
  "homepage": "https://github.com/theme-kaze/hexo-theme-Kaze#readme"
}
```

### Python

```python
import requests
import re
import sys
import os
url = 'https://twoshot.hgame.n3ko.co/'
headers = {
    'Content-Type': 'application/x-www-form-urlencoded',
    'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/71.0.3578.98 Safari/537.36',
}
p = requests.get(url+'random.php?times=228', headers=headers)
randnum = re.findall(r'\d*', p.text)[1:-2:2]
firstnum = randnum[0]
lastnum = randnum[227]
content = os.popen("python3 ./reverse_mt_rand.py " +
                   firstnum+' '+lastnum+' 0 0').read()
q = requests.post(url+'/verify.php', headers=headers, data={'ans': content})
print(q.text)
```

### Go

```go
// backup my secret key into DB
_, err = db.Exec(fmt.Sprintf(`INSERT INTO secret(secret) VALUES('%s');`, secretKey))
if err != nil {
    return err
}

if u.TotalBalance > 999999 || win {
    flag = os.Getenv("flag")
} else {
    flag = "nothing to show, to be a winner"
}
```

<script>
  function changePrismTheme(e) {
    let text = e.target.innerHTML;
    let linkList = document.head.getElementsByTagName('link');
    for(let item of linkList) {
      if(item.dataset.prism) {
        document.head.removeChild(item);
      }
    }
    let link = document.createElement('link');
    link.rel = 'stylesheet';
    link.dataset.prism = text;
    if(text === 'default') {
      text = 'prism';
    } else {
      text = 'prism-' + text;
    }
    link.href='/js/lib/prism/' + text +'.min.css';
    document.head.appendChild(link);
  }
  setTimeout(() => {
    let buttonList = document.getElementsByClassName('postbutton');
    Array.prototype.forEach.call(buttonList, item => {
      item.onclick = changePrismTheme;
    });
  }, 0);
</script>

