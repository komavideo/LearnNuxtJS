接收多个参数
==========

## 知识点

* 从URL中接收多个参数，非常常用，必会技术哦！

## 实战演习

### pages/_tag/index.vue

```html
<template>
    <div>
        <h1>商品一览({{this.$route.params.tag}})</h1>
        <hr>
        <ul>
            <li><a :href="this.$route.params.tag + '/Zelda'">Zelda</a></li>
            <li><a :href="this.$route.params.tag + '/Mario'">Mario</a></li>
        </ul>        
    </div>
</template>
```

#### 访问方式

http://ip:port/ps5  

### pages/_tag/_name.vue

```html
<template>
    <div>
        <h1>商品详细</h1>
        <hr>
        <div v-if="this.$route.params.name">
            标签名：{{ this.$route.params.tag }} / {{ this.$route.params.name }}
        </div>
    </div>
</template>
```

#### 访问方式

http://ip:port/ps5/zelda  

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P