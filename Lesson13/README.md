使用vuex状态管理
===============

## 知识点

* 使用vuex状态管理开发应用

## 官网

https://nuxtjs.org/guide/vuex-store

## 实战演习

### store/index.js

```javascript
export const state = () => ({
    counter: 0
})

export const mutations = {
    increment(state) {
        state.counter++
    }
}
```

### pages/about.vue

```html
<template>
    <div>
        <h1>about</h1>
        <button @click="increment">喜加一</button>
        <div>{{counter}}</div>
    </div>
</template>
<script>
    import { mapState } from 'vuex'
    import { mapMutations } from 'vuex'
    export default {
        name: "about",
        components: {
            // HelloWorld
        },
        data: function () {
            return {};
        },
        props: {},
        computed: {
            // 映射store.state
            ...mapState({
                counter: (state) => state.counter,
            }),
        },
        methods: {
            // 映射store.mutations
            ...mapMutations({
                increment: 'increment'
            }),
        },
    };
</script>
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P