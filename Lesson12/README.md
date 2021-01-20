Nuxt.js插件的使用 - vue-tooltip
==============================

## 知识点

* 使用插件(plugins)为Nuxt.js增加功能

### 官网

https://go.nuxtjs.dev/config-plugins

## 实战演习

### 安装Vue插件 - vue-tooltip

★注意：该插件与BootstrapVue冲突★

```bash
$ npm install v-tooltip --save
# SCSS支持
$ npm install --save-dev sass sass-loader fibers
```

### plugins/vue-tooltip.js

```javascript
import Vue from 'vue'
import VTooltip from 'v-tooltip'

Vue.use(VTooltip)
```

### nuxt.config.js

```javascript
    plugins: [
        { src: '~/plugins/vue-tooltip.js', mode: 'client' },
    ]
```

### pages/about.vue

```html
<template>
    <div>
        <h1>关于</h1>
        <hr>
        <div align="center">
            <button v-tooltip.top="msg">神圣的按钮</button>
            <button v-tooltip.bottom="msg">神圣的按钮</button>
        </div>
    </div>
</template>

<script>
    export default {
        data: function () {
            return {
                msg: "嘿！你又成功了！"
            }
        },
    };
</script>

<style lang="scss">
    .tooltip {
        display: block !important;
        z-index: 10000;

        .tooltip-inner {
            background: black;
            color: white;
            border-radius: 16px;
            padding: 5px 10px 4px;
        }

        .tooltip-arrow {
            width: 0;
            height: 0;
            border-style: solid;
            position: absolute;
            margin: 5px;
            border-color: black;
            z-index: 1;
        }

        &[x-placement^="top"] {
            margin-bottom: 5px;

            .tooltip-arrow {
                border-width: 5px 5px 0 5px;
                border-left-color: transparent !important;
                border-right-color: transparent !important;
                border-bottom-color: transparent !important;
                bottom: -5px;
                left: calc(50% - 5px);
                margin-top: 0;
                margin-bottom: 0;
            }
        }

        &[x-placement^="bottom"] {
            margin-top: 5px;

            .tooltip-arrow {
                border-width: 0 5px 5px 5px;
                border-left-color: transparent !important;
                border-right-color: transparent !important;
                border-top-color: transparent !important;
                top: -5px;
                left: calc(50% - 5px);
                margin-top: 0;
                margin-bottom: 0;
            }
        }

        &[x-placement^="right"] {
            margin-left: 5px;

            .tooltip-arrow {
                border-width: 5px 5px 5px 0;
                border-left-color: transparent !important;
                border-top-color: transparent !important;
                border-bottom-color: transparent !important;
                left: -5px;
                top: calc(50% - 5px);
                margin-left: 0;
                margin-right: 0;
            }
        }

        &[x-placement^="left"] {
            margin-right: 5px;

            .tooltip-arrow {
                border-width: 5px 0 5px 5px;
                border-top-color: transparent !important;
                border-right-color: transparent !important;
                border-bottom-color: transparent !important;
                right: -5px;
                top: calc(50% - 5px);
                margin-left: 0;
                margin-right: 0;
            }
        }

        &[aria-hidden='true'] {
            visibility: hidden;
            opacity: 0;
            transition: opacity .15s, visibility .15s;
        }

        &[aria-hidden='false'] {
            visibility: visible;
            opacity: 1;
            transition: opacity .15s;
        }
    }
</style>
```

## 课程文件

https://github.com/komavideo/LearnNuxtJS

## 小马视频频道

http://komavideo.com

## 小马部落

https://discord.gg/VSKw72P