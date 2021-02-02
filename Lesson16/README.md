模块使用：nuxt-content - 快速开发 Markdown 语法的网页
=================================================

## 知识点

* nuxt-content 模块的安装与使用

## 官网

https://content.nuxtjs.org/

## 实战演习

```bash
# 初始化工程
$ npx create-nuxt-app myweb
$ cd myweb
# 安装 nuxt-content (手工导入方式)
$ npm install @nuxt/content
$ nano nuxt.config.js
...
  modules: [
    '@nuxt/content'
  ],
  content: {
    // Options
  },
...
```

## 建立文档

### /content/nodejs/

#### Lesson01.md

```
---
title: Node.js课程01
position: 1
---
Node.js学习入门-01
=============

I like Node.js.
```

Lesson02.md, Lesson03.md, ...

### /pages/index.vue

```html
<template>
    <div class="container">
        <div>
            <h1 class="title">myweb</h1>
        </div>
        <div>
            <ul>
                <li v-for="lesson in list" :key="lesson.title">
                    <NuxtLink :to="'/lesson' + lesson.path">{{lesson.title}}</NuxtLink>
                </li>
            </ul>
        </div>
        <hr />
    </div>
</template>

<script>
export default {
    async asyncData({ $content }) {
        const lessonList = await $content("nodejs")
            .sortBy("position", "asc")
            .fetch();
        console.log(lessonList);
        return {
            list: lessonList,
        };
    },
};
</script>
```

### /pages/lesson/_name/_id.vue

```html
<template>
    <div>
        <div>params.name: {{ this.$route.params.name }}</div>
        <div>params.id: {{ this.$route.params.id }}</div>
        <hr />
        <div>
            <nuxt-content :document="page" />
        </div>
        <hr />
        <nuxt-link to="/">Home</nuxt-link>
    </div>
</template>

<script>
export default {
    name: "lesson",
    async asyncData({ $content, params }) {
        const page = await $content(`${params.name}/${params.id}`).fetch();
        return {
            page,
        };
    },
};
</script>
```

### layouts/default.vue

```html
    <div style="background-color: #35495e;color:white">NavBar</div>
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P
