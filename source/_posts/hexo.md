---
title: hexo
date: 2020-05-03 18:30:56
tags:
  - hexo
---

[参照melody主题官方文档](https://molunerfinn.com/hexo-theme-melody-doc/)


# 1. 快速开始
查找您的hexo工作文件夹
```
git clone -b master https://github.com/Molunerfinn/hexo-theme-melody themes/melody
```

*****


# 2. 特殊功能

## 1. 折叠代码块
```
<details>
    <summary>这是折叠代码块的标题</summary>
``` 
这是代码块的内容一
这是代码块的内容二
``` 
</details>
```
**效果：**
<details>
    <summary>这是折叠代码块的标题</summary>
```
这是代码块的内容一
这是代码块的内容二
```
</details>


## 2. hexo添加图片配置
安装图片插件(以下皆可)：
- `npm install https://github.com/7ym0n/hexo-asset-image --save`
- `npm install https://github.com/CodeFalling/hexo-asset-image --save`

插入图片的几种方法：
```md
1. ![img](celery/celery.jpg "celery流程")
2. <img src="celery/celery.jpg" width=100px height="100px" title="celery流程">
3. {% asset_img test.jpg This is an test image %}
其中test.jpg就是你要引用的图片，我这里就是test.jpg，后面的This is an test image是图片描述，可以自己修改。
```


*****


# 3. 主题页

## 1. 标签
1. 进入您的hexo博客根文件夹。
2. 类型 `hexo new page tags`
3. 你会找到 `source/tags/index.md`
4. 修改 `index.md`
```md
---
title: tags
date: 2018-01-05 00:00:00
type: "tags"
---
```


## 2. 分类
1. 进入您的hexo博客根文件夹。
2. 类型 `hexo new page categories`
3. 你会找到 `source/categories/index.md`
4. 修改 `index.md`
```md
---
title: categories
date: 2018-01-05 00:00:00
type: "categories"
---
```


## 3. 创建幻彩灯界面
1. 进入您的hexo博客根文件夹
2. 类型 `hexo new page slides`
3. 你会找到 `source/slides/index.md`
4. 修改 `index.md`
```md
---
title: Slides 
date: 2018-01-05 00:00:00
type: "slides"
---
```


## 4. 幻彩灯
幻灯片页面可让您使用Reveal.js编写markdown和输出，以制作漂亮的幻灯片页面。
**设置 melody.yml**
```yml
slide:
  separator: ---
  separator_vertical: --
  charset: utf-8
  theme: black
  # optional
  mouseWheel: false
  transition: slide
  transitionSpeed: default
  parallaxBackgroundImage: ''
  parallaxBackgroundSize: ''
  parallaxBackgroundHorizontal: null
  parallaxBackgroundVertical: null
```
> 有关Reveal.js的配置，请参见https://github.com/hakimel/reveal.js#configuration


## 5. 使用幻彩片布局创建帖子
只需md照常创建一个文件。`layout: slides`在hexo post文件的中添加一个称为的属性front matter
> 您还可以slide通过在发布文件的中添加幻灯片选项来设置具有特定配置的幻灯片页面front matter。
<details>
    <summary>特定配置的幻灯片页面</summary>
```md
---
title: hexo-theme-melody v1.5 supports slides & iframe
date: 2018-03-06 19:57:52
tags: hexo
layout: slides
slide:
  theme: night
  separator: ===
  separator_vertical: ==
---

### hexo-theme-melody <small>v1.5</small>
<!-- .slide: data-background="#49B1F5" -->

Supports iframe & slides. You can use a layout called `slides` to enabled the slides layout.

Also you can add a `iframe` front-matter with the `slides` layout in your `md` file to enable the iframe page.

### Steps
<!-- .slide: data-transition="concave" data-background="#C7916B" -->

#### 1. Add a slides page

// ......

==

// ......

===

#### 2. Add the layout type
<!-- .slide: data-transition="fade" data-background="#00C4B6" -->

// ......
```
</details>


## 6. 使用iframe界面创建帖子
如果要在iframe中添加所需的网站，请尝试以下操作(布局必须为幻彩灯)：
```md
title: hexo-theme-melody v1.5 supports iframe & slides
date: 2018-03-06 19:57:52
layout: slides
iframe: https://the-url-whatever-you-like
---
```


## 7. 图库
1. 进入您的hexo博客根文件夹。
2. 类型 `hexo new page gallery`
3. 你会找到 `source/gallery/index.md`
4. 修改 `index.md`
```md
---
title: Gallery 
date: 2018-01-05 00:00:00
type: "gallery"
---
```
然后主题旋律支持gallery为您命名的标记，以gallery-item在markdown文件中创建。

修改source/gallery/index.md您之前创建的gallery标签，添加标签。
<details>
    <summary>例如</summary>
```md
---
title: Gallery 
date: 2018-01-05 00:00:00
type: "gallery"
---
{% gallery img-url [title] %}
{% gallery https://ws1.sinaimg.cn/large/8700af19gy1fp5i6o2vghj20ea0eajse melody %}
{% gallery https://user-images.githubusercontent.com/12621342/37325500-23e8f77c-26c9-11e8-8e24-eb4346f1fff5.png background %}
{% gallery https://ws1.sinaimg.cn/large/8700af19gy1fp5i64zaxqj20b40b474b demo1 %}
{% gallery https://ws1.sinaimg.cn/large/8700af19ly1fn2h26q32uj21120kudqq demo2 %}
{% gallery https://ws1.sinaimg.cn/large/8700af19ly1fnhdaimi40j218g0p0dic demo3 %}
{% gallery https://ws1.sinaimg.cn/large/8700af19ly1fn2i5kjh2pj21120kuncd %}
```
</details>



## 8. 404界面
1. 进入您的hexo博客根文件夹。
2. 类型 `hexo new page 404`
3. 你会找到 `source/404/index.md`
4. 修改 `index.md`
```md
---
title: 404
date: 2019-10-13 15:49:05
layout: 404
permalink: /404
---
```

*****


# 4. 主题配置

## 1. 语言
设置根`_config.yml`，而不是根`melody.yml`！
```yml
language: en    # 还有default和zh-Hans，可自由设置
```

## 2. 代码自动换行
默认情况下，`hexo-highlight`以长行生成代码。如果您不想在代码区域中使用滚动条，则可以启用此功能。

设置 `melody.yml`
```yml
code_word_wrap: true
```

找到根 `_config.yml`，将`line_number`改为`false`：
```yml
highlight:
  enable: true
  line_number: false # <- change this
  auto_detect: false
  tab_replace:
```


## 3. 菜单
在右上方区域中，有导航菜单项。HEXO有默认路径/和/archives。如果要添加更多菜单项，例如标签和类别，请遵循以下步骤：
1. 进入您的hexo博客根文件夹。
2. 类型 `hexo new page tags`
3. 你会找到 `source/tags/index.md`
4. 修改 `index.md`
```
---
title: tags
date: 2018-01-05 00:00:00
type: "tags"
---
```
然后设置 `melody.yml`
```yml
menu:
  Home: /
  Archives: /archives
  Tags: /tags
  Categories: /categories
```


## 4. 顶图
`Top Img`是`theme-melody`最神奇的选择。它可以具有`true`或`false`或`specific img url`值。

设置 `melody.yml`
```yml
top_img: true    # 索引网站界面图片和帖子界面图片都显示默认
top_img: false  # 索引网站界面图片显示默认，帖子界面图片不显示
top_img: https://xxxxx.jpg  # 索引网站界面图片和帖子界面图片显示xxxxx.jpg
```
设置特定后置项目的自身top-img, 只需top_img在特定md文件的帖子标题中添加＆网址
```
title: Hi, theme-melody!
tags:
  - hexo
  - hexo theme
top_img: https://xxxxxxx.jpg   # < add top_img to here
date: 2017-09-07
---
```

## 5. 侧边栏设置
由于`v1.7.0`，您可以将设置`melody.yml`为控制边栏以自动显示或不显示在特定页面中。默认`sidebar_display`值为`post`，这意味着侧栏将自动显示在帖子页面中。
```yml
sidebar_display: all    # 所有页面都会自动显示侧边栏
sidebar_display: index  # 仅索引页面会自动显示侧边栏
sidebar_display: post  # 仅帖子页面会自动显示侧边栏
sidebar_display: index-none  # 仅索引页面不会自动显示侧边栏
sidebar_display: post-none  # 仅帖子页面不会自动显示侧边栏
sidebar_display: phidden  # 所有页面不会自动显示侧边栏
```

## 6. 头像
设置`melody.yml`。请选择长度和宽度相等的图像。
```yml
avatar: https://xxxx.jpg
```


## 7. 跟着我
设置`melody.yml`。
```yml
follow:
  enable: true
  url: 'https://github.com/USERNAME'
  text: 'Follow Me'
```

## 8. 友情链接
在边栏中，您可以设置一些指向您的朋友或某些网页的链接。格式为`name: url`
设置 `melody.yml`
```yml
links_title: Links   # Set the links title
links:
  name: https://url.com
```

## 9. Toc
您可以为自己的帖子提供目录目录。它在边栏中，并且将根据您的滚动顶部自动扩展标题。
设置 `melody.yml`
```yml
toc:
  enable: true # 是否显示帖子目录
  number: true # v1.5.6版本后，是否显示目录列表编号
```
设置特定后项的自身toc编号
```md
title: Hi, theme-melody!
tags:
  - hexo
  - hexo theme
toc_number: false   # 之后，您的特定帖子将拥有自己的顶数控件，而不是主题toc-number值
date: 2017-09-07
---
```


## 10. Since
`Since`是向人们显示您网站年龄的一种选择。它的位置在页面的底部。
设置 `melody.yml`
```yml
since: 2013
```

## 11. Footer Custom Text
`footer_custom_text`是用于在页脚区域显示一些文本的选项。它支持HTML。

设置 `melody.yml`
```yml
footer_custom_text: Hi, welcome to my <a href="https://molunerfinn.com">blog</a>!
footer_custom_text: hitokoto    # 1.7.0版本，如果设置hitokoto，则会随机生成文本
```


*****


# 5. 第三方包支持

## 1. 本地搜索
1. 安装 `npm install hexo-generator-search --save`
2. 设置 `melody.yml`
```yml
local_search:
enable: true # or false
labels:
    input_placeholder: Search for Posts
    hits_empty: "We didn't find any results for the search: ${query}" # if there are no result
```

## 2. 即时贴
具有可以使指定博客显示到首页的功能
1. 转到hexo网站文件夹
2. `npm uninstall hexo-generator-index --save` 然后 `npm install hexo-generator-index-pin-top --save`
3. 您可以将`top: True`字段添加到帖子的最前面以将其固定。
例：
```md
title: xxxx
tags:
  - xxx
date: 2018-08-08 08:08:08
top: True
---
// ....
```

## 3. 分享系统
**Sharejs**
配置`melody.yml`
```yml
sharejs:
  enable: true
  disabled_sites: 你不想分享的站点
```

*****


# 6. 附加包支持

## 1. PWA
要具有的PWA功能theme-melody，您需要执行以下操作：

1. 转到hexo网站文件夹
2. `npm install hexo-offline --save` 要么 `yarn add hexo-offline`
3. 修改`_config.yml` 将以下内容添加到站点`_config.yml`。
```yml
# offline config passed to sw-precache.
offline:
  maximumFileSizeToCacheInBytes: 10485760 # 缓存的最大文件大小，以字节为单位
  staticFileGlobs:
    - public/**/*.{js,html,css,png,jpg,gif,svg,webp,eot,ttf,woff,woff2}
  # 静态文件合集，如果你的站点使用了例如webp格式的文件，请将文件类型添加进去。
  stripPrefix: public
  verbose: true
  runtimeCaching:
    # CDNs - should be cacheFirst, since they should be used specific versions so should not change
    - urlPattern: /* # 如果你需要加载CDN资源，请配置该选项，如果没有，可以不配置。
      handler: cacheFirst
      options:
        origin: your_websie_url # 可替换成你的 url
```
4. 打开中的pwa选项`melody.yml`。
```yml
pwa:
  enable: true
  manifest: # manifest.json的url, 通常可以设置成 /manifest.json
  # 从v1.5.6开始你可以修改PWA的主题色和icon了。
  # 如果不明白这些有什么用，或者不想配置可以忽视下面的配置
  # See https://realfavicongenerator.net/
  # theme_color: "#1B9EF3"
  # apple_touch_icon: /apple-touch-icon.png
  # favicon_32_32: /favicon-32x32.png
  # favicon_16_16: /favicon-16x16.png
  # mask_icon: /safari-pinned-tab.svg
```
5. 在`source/`目录中创建一个`manifest.json`文件。

    <details>
        <summary>manifest.json</summary>
```json
{
    "name": "string",
    "short_name": "Junzhou",
    "theme_color": "#49b1f5",
    "background_color": "#49b1f5",
    "display": "standalone",
    "scope": "/",
    "start_url": "/",
    "icons": [ 
        {
          "src": "images/pwaicons/36.png",
          "sizes": "36x36",
          "type": "image/png"
        },
        {
            "src": "images/pwaicons/48.png",
          "sizes": "48x48",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/72.png",
          "sizes": "72x72",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/96.png",
          "sizes": "96x96",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/144.png",
          "sizes": "144x144",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/192.png",
          "sizes": "192x192",
          "type": "image/png"
        },
        {
            "src": "images/pwaicons/512.png",
            "sizes": "512x512",
            "type": "image/png"
          }
      ],
      "splash_pages": null
}
```
</details>

## 2. Live2D Animated model pendant
使用以下命令安装`Live2D model`，该模块需要root通过终端在博客目录中执行：
安装：
- `npm install --save hexo-helper-live2d`
卸载：
- `npm uninstall hexo-helper-live2d`

> 配置您喜欢的动画模型
1. [对应模块下载](https://github.com/xiazeyu/live2d-widget-models)
   * [模型预览](https://www.linuxwf.com/2020/04/09/Hexo添加Live2d看板动画效果/#添加Live2d看板动画)
2. 例如，我使用tororo(`npm install live2d-widget-model-tororo`)，可以直接在上面的下载界面中：
   1. 手动下载完成后，将所有文件复制`packages`到`node_moduels`博客根目录下的文件夹中。
   2. 也可以使用包管理器进行安装。命令格式：`npm install model package name`也将安装在node_moduels目录中。
3. 打开`_config.yml`博客根目录的配置文件，并添加以下内容：
```yml
# Live2D
live2d:
  enable: true
  scriptFrom: local # 默认
  pluginRootPath: live2dw/ # 插件在站点上的根目录
  pluginJsPath: lib/ # 脚本文件相对与插件根目录路径
  pluginModelPath: assets/ # 模型文件相对与插件根目录路径
  tagMode: false  # 标签模式, 是否仅替换 live2d tag标签而非插入到所有页面中
  debug: false  # 调试, 是否在控制台输出日志
  model:   
    use: live2d-widget-model-tororo # 下载的动画模型名称
  display:
    superSample: 2
    width: 150
    height: 300
    position: right # 模型显示在网页上的位置
    hOffset: 0  # 看板娘x轴位置
    vOffset: -20  # 看板娘y轴位置
  mobile:
    show: true # 是否在移动设备上显示
    scale: 0.5 # 移动设备上的缩放
react:
    opacityDefault: 0.7
    opacityOnHover: 0.2
```