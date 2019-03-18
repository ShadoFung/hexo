---
layout: post
title: "Hexo-Next主题配置"
date: 2019-02-22
excerpt: "有一个已经有序的数据序列，要求在这个已经排好的数据序列中插入一个数，但要求插入后此数据序列仍然有序，这个时候就要用到一种新的排序方法——插入排序法"
tags: [博客, Next]
categories: 博客
comments: true
---

## 搜索功能
### 在Hexo根目录下执行 npm install hexo-generator-searchdb --save
### blog下的_config.yml文件编辑
```
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```
### /blog/themes/next下的_config.yml文件编辑
```
local_search:
    enable: true
```

## RSS订阅
### 在Hexo根目录下执行 npm install hexo-generator-feed --save
### blog下的_config.yml文件编辑
```
# RSS订阅
plugin:
- hexo-generator-feed

# RSS
feed:
  type: atom
  path: atom.xml
  limit: 20
```
### /blog/themes/next下的_config.yml文件编辑
```
rss: /atom.xml
```

## 发布到Github
### 在Hexo根目录下执行 npm install --save hexo-deployer-git
### 自动关联域名 创建../Hexo根目录/source/CNAME 内容为域名，如：`www.mingdong.online`
### hexo d

## 文章字数统计和阅读时间统计
### https://github.com/theme-next/hexo-symbols-count-time
### 在Hexo根目录下执行 npm install hexo-symbols-count-time --save
### blog下的_config.yml文件编辑
```
symbols_count_time:
  symbols: true
  time: true
  total_symbols: true
  total_time: true
```

## 博客中插入图片
### 在Hexo根目录下执行 npm install hexo-asset-image --save
### blog下的_config.yml文件编辑
```
post_asset_folder: true
```

## live2d
### https://github.com/EYHN/hexo-helper-live2d/blob/master/README.md
### 在Hexo根目录下执行 npm install --save hexo-helper-live2d
### blog下的_config.yml文件编辑
```
live2d:
  enable: true
  scriptFrom: local
  pluginRootPath: live2dw/
  pluginJsPath: lib/
  pluginModelPath: assets/
  tagMode: false
  debug: false
  model:
    use: live2d-widget-model-wanko
  display:
    position: right
    width: 150
    height: 300
  mobile:
    show: true
```

## aplayer
### https://github.com/MoePlayer/hexo-tag-aplayer
### 在Hexo根目录下执行 npm install --save hexo-tag-aplayer
### 使用
#### {% aplayer title author url [picture_url, narrow, autoplay, width:xxx, lrc:xxx] %}
- title : 曲目标题
- author: 曲目作者
- url: 音乐文件 URL 地址
- picture_url: (可选) 音乐对应的图片地址
- narrow: （可选）播放器袖珍风格
- autoplay: (可选) 自动播放，移动端浏览器暂时不支持此功能
- width:xxx: (可选) 播放器宽度 (默认: 100%)
- lrc:xxx: （可选）歌词文件 URL 地址
当开启 Hexo 的 文章资源文件夹`post_asset_folder: true` 功能时，可以将图片、音乐文件、歌词文件放入与文章对应的资源文件夹中，然后直接引用：

`{% aplayer "Caffeine" "Jeff Williams" "caffeine.mp3" "picture.jpg" "lrc:caffeine.txt" %}`
