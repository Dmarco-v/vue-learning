# vue-learning
## 一、入门

### 1.简介

官网文档：https://cn.vuejs.org/v2/guide/

Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

### 2.基础

**文件结构**

template，style，script

**模板语法**

vue.js的核心就是允许采用简单的模板语法声明式地将数据渲染进DOM节点。

```vue
<template>
	<div id="app">
        {{msg}}
    </div>
</template>
<script>
	var app=new Vue({
        el:"#app",
        data:{
            msg:'Hello,Vue!'
        }
    })
</script>
```

**常用指令**

- v-bind，简写为" : " 绑定属性。常用于绑定class，style等属性
- v-on: click ，简写为"@click"，监听事件

**侦听属性与计算属性**

watch中定义的属性为侦听属性，当属性值发生变化，则会调用该方法重新渲染。（使用场景：异步渲染）

computed中定义的属性为计算属性，当内部包含的对象（此处的app）属性发生变化，计算属性的值就会重新渲染，而其他属性（如此处的another）发生变化，计算属性的值不会相应变化。（使用场景：数据联动）

```Vue
<script>
  var another='another';
  var app=new Vue({
    el:"#app",
    data:{
      msg:"Hello,Vue!"
    },
    watch:{
      msg: function (newval,oldval) {
        console.log('newval is: '+newval);
        console.log('oldval is: '+oldval);
      },
    },
    computed:{
      msg1:function () {
        return 'computed: '+ this.msg + another;
      }
    },
  })
</script>
```

**条件渲染与循环渲染**

- v-if，v-else-if，v-else。v-if ="js表达式" 满足条件时执行渲染
- v-show。满足条件时显示，不满足则不显示
- v-for。循环渲染。

## 二、核心

### 1.vue-cli

常用指令：

- vue create project-name，创建工程。也可以使用vue ui (vue-cli3) 可视化创建工程。
- npm run dev(vue-cli2)/ npm run serve(vue-cli3)，启动项目。

相关配置：

- Babel：js编译器，使项目可以兼容ES6以上的高级js语法。
- npm/yarn 包管理工具
- CSS Pre-processors ：CSS预编译（Sass/SCSS选择node-sass实时编译）
- Router：路由管理器
- Vuex：状态管理
- ESLint：可配置的Js语法规则和代码风格检查工具
- Unit Testing：单元测试

### 2.组件化

组件化的目的：

- 实现功能模块的复用
- 提高执行效率
- 开发单页面（仅局部刷新）复杂应用。

### 3.Vue-router

路由管理。

- 在router\index.js中注册路由
- 在用到跳转按钮的页面用<router-link>标签设置跳转的路由。

### 4.Vuex

Vuex是为Vue.js开发的状态管理模式。为了实现对组件状态的集中管理，使得组件状态的改变遵循统一的规则。









**附**：

[vue编码风格指南](https://cn.vuejs.org/v2/style-guide/index.html)





