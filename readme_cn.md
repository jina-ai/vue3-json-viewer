# vue3-json-viewer

简单易用的json内容展示组件,适配vue3和vite。
在使用vue3+vite开发时，发现需要用到显示json数据组件，发现vue-json-viewer只能兼容vue2，于是花了一个小时，重写的vue3的适配。
原作者：[github](https://github.com/chenfengjw163/vue-json-viewer)

## 安装

需要依赖clipboard，先安装clipboard

```
$ npm install clipboard --save
```

再安装vue3-json-viewer

```
$ npm install vue3-json-viewer --save
```
## 近期更新
- 暗夜主题支持
- 添加key节点点击事件
- 支持正则表达式类型
  
## 使用

main.js

```js
import { createApp } from 'vue'
import App from './App.vue'
import JsonViewer from "vue3-json-viewer"
// if you used v1.0.5 or latster ,you should add import "vue3-json-viewer/dist/index.css"
import "vue3-json-viewer/dist/index.css"
const app = createApp(App)
//全局引入
app.use(JsonViewer)
app.mount('#app')
```

App.vue

``` html
<template>
<div class="box">
  <h2>明亮</h2>
 <JsonViewer :value="jsonData" copyable boxed sort theme="jv-light"/>
  <h2>暗黑</h2>
   <JsonViewer :value="jsonData" copyable boxed sort theme="jv-dark"/>
</div>
 
</template>

<script setup>
//组件引入
import {JsonViewer} from "vue3-json-viewer"

import "vue3-json-viewer/dist/index.css";
import { reactive, ref } from "vue";
let obj = {
  name: "qiu",//字符串
  age: 18,//数组
  isMan:false,//布尔值
  date:new Date(),
  fn:()=>{},
  arr:[1,2,5]
};
const jsonData = reactive(obj);
</script>

<style>
.box{
    margin-top: 1rem;
}
</style>
```

![](./img/demo.png)