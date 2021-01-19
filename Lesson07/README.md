错误处理页面
==========

## 知识点

* 错误处理页面的使用方法

## 实战演习

### layouts/error.vue

```html
<template>
    <div>
        <h1>对不起，出错啦！</h1>
        <!-- {{error}} -->
    </div>
</template>
<script>
    export default {
        props: ['error'],
        layout: 'error_layout' // 不指定错误页面布局的话，则会使用default默认布局
    }
</script>
```

### layouts/error_layout.vue

```html
<template>
    <div>
        <header>
            <h1>错误页面</h1>
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