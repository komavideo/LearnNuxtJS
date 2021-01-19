Axios模块的使用
==============

## 知识点

* 异步通信模块Axios的使用

## 官网

https://axios.nuxtjs.org/

## 实战演习

### 使用axios模块

```bash
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

### pages/about.vue

```html
<template>
    <div>
        <h1>关于</h1>
        <hr>
        <div>
            <b-button variant="success" @click="fetchGames()">装载服务器数据</b-button>
            <hr>
            <ul>
                <li v-for="item in list">{{item.name}} - {{item.price}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        data: function () {
            return {
                list: []
            }
        },
        methods: {
            async fetchGames() {
                const data = await this.$axios.$get('https://raw.githubusercontent.com/komavideo/LearnNuxtJS/main/games.json')
                console.log(data)
                this.list = data
            }
        }
    };
</script>
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P