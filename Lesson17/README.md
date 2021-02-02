模块使用：nuxt-axios - 安装与设置
==============================

## 知识点

* 模块使用：nuxt-axios 的安装与设置

## 官网

https://axios.nuxtjs.org/

## 实战演习

### 使用axios模块

```bash
# 初始化工程
$ npx create-nuxt-app myweb
$ cd myweb
# 导入 nuxt-axios (手工导入方式)
$ npm install @nuxtjs/axios --save
$ nano nuxt.config.js
...
    modules: [
        '@nuxtjs/axios',
    ],
    axios: {
        // https://axios.nuxtjs.org/options/
    },
...
```

## 建立 axios 插件

### /plugins/axios.js

```javascript
export default function ({ $axios }) {
    $axios.onError(error => {
        nuxtError({
            statusCode: error.response.status,
            message: error.message,
        });
        return Promise.resolve(false);
    })

    $axios.onRequest((config) => {
        // Adds header: `Authorization: Bearer 1234567890` to all requests
        $axios.setToken('1234567890', 'Bearer')
    });
}
```

### 配置 nuxt.config.js 

```javascript
...
    plugins: [
        { src: '~/plugins/axios.js' },
    ],
...
    axios: {
        baseURL: process.env.AXIOS_BASE_URL || 'http://127.0.0.1:3000',
        https: process.env.AXIOS_HTTPS || false,
    },
...
```

### 配置环境变量 .env

```
AXIOS_BASE_URL=https://api.komavideo.com
AXIOS_HTTPS=true
```

### /pages/index.vue

```html
<template>
    <div class="container">
        <div>
            <h1 class="title">myweb</h1>
            <hr />
            <div>
                {{ content }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    async asyncData({ $axios }) {
        const content = await $axios.$get("/test.txt");
        return { content };
    },
};
</script>
```

### /static/test.txt

```
test123
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P