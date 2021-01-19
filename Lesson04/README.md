秒速建立网页
==========

## 知识点

* 在Nuxt.js工程中快速建立网页
* 定制网页的布局 - layout
* 路由的自动配置

## 实战演习

### pages/about.vue

```html
<template>
    <div>
        <h1>关于(About)</h1>
    </div>
</template>
```

### pages/article/index.vue

```html
<template>
    <div>
        <h1>我的文章</h1>
    </div>
</template>
```

### pages/article/list.vue

```html
<template>
    <div>
        <h1>文章列表</h1>
        <ul>
            <li>我爱Nuxt.js</li>
            <li>我爱Vue.js</li>
            <li>我带尤大婶</li>
        </ul>
    </div>
</template>
```

## 定制网页布局

### layouts/default.vue

```html
<template>
    <div>
        <header>
            <h1>我的网站</h1>
            <a href="/">首页</a>
            <a href="/about">关于</a>
            <a href="/article">文章</a>
            <a href="/article/list">列表</a>
        </header>
        <Nuxt />
    </div>
</template>
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P