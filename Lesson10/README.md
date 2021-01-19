Nuxt.js模块的使用 - Bootstrap
===========================

## 知识点

* 扩展Nuxt的核心功能，使用Nuxt模块

## 官网

https://modules.nuxtjs.org/

## 实战演习

### 使用bootstrap-vue模块

```bash
$ npm install bootstrap-vue --save
$ nano nuxt.config.js
...
    modules: [
        'bootstrap-vue/nuxt',
    ],
    bootstrapVue: {
        // Install the `IconsPlugin` plugin (in addition to `BootstrapVue` plugin)
        icons: false
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
            <b-button>Button</b-button>
            <b-button variant="danger">按钮1</b-button>
            <b-button variant="success">按钮2</b-button>
            <b-button variant="outline-primary" @click="helo()">按钮3</b-button>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            helo: function () {
                alert("helo bootstrap-vue @nuxt.js")
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