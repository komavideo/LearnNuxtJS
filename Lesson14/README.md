nuxt.js + vuex + todos 简单实现
==============================

## 知识点

* 使用 Nuxt.js + Vuex 简单实现 todos 应用

## 实战演习

### store/todos.js

```javascript
export const state = () => ({
    list: []
})

export const mutations = {
    add(state, text) {
        state.list.push({
            text,
            done: false
        })
    },
    remove(state, { todo }) {
        state.list = state.list.filter(n => !n.done);
    },
    toggle(state, todo) {
        todo.done = !todo.done
    }
}
```

### pages/todos.vue

```html
<template>
    <div style="margin: 30px;">
        <h1>todos</h1>
        <hr>
        <div>
            <input @keyup.enter="addTodo" placeholder="动弹一下...">
            <button @click="remove">删除</button>
        </div>
        <ol>
            <li v-for="todo in list" :key="todo.text">
                <label>
                    <input :checked="todo.done" @change="toggle(todo)" type="checkbox">
                    <span :class="{ done: todo.done }">{{ todo.text }}</span>    
                </label>
            </li>
        </ol>
    </div>
</template>

<script>
    // https://vuex.vuejs.org/zh/
    import { mapState } from 'vuex'
    import { mapMutations } from 'vuex'

    export default {
        name: "todos",
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
                list: (state) => state.todos.list,
            }),
        },
        methods: {
            addTodo(e) {
                this.add(e.target.value)
                e.target.value = ''
            },
            // 映射store.mutations
            ...mapMutations({
                add: 'todos/add',
                remove: 'todos/remove',
                toggle: 'todos/toggle',
            }),
        },
    };
</script>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P