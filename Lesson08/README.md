接收URL参数
==========

## 知识点

* 接收用户通过URL传来的参数

## 实战演习

### pages/item/_id.vue

```html
<template>
    <div>
        <h1>商品</h1>
        <hr>
        <div v-if="this.$route.params.id">
            商品ID：{{ this.$route.params.id }}
        </div>
    </div>
</template>
```

### 访问方式

http://ip:port/item/1  
http://ip:port/item/2  
http://ip:port/item/3  

## 限定数值类型参数

```javascript
<script>
    export default {
        validate({ params }) {
            return /^\d+$/.test(params.id)
        }
    }
</script>
```

### 参照文档

https://nuxtjs.org/docs/2.x/components-glossary/pages-validate

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P