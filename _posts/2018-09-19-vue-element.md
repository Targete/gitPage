---
layout: post
title: pip更新
tags: vue js elementUI 
math: true
date: 2018-09-19 22:43 +0800
---
## vue-element后台系统总结
### 主页面滚动条消除
> 在全局写入样式消除margin 和 padding height:100%

```css
* {
margin:0;
padding:0;
}
html,body,#app {
  height: 100%;
}
```
### relative
![relative.png](https://upload-images.jianshu.io/upload_images/2823133-d5cab549d2a9ac30.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### px2rem配置
> 在vue.config.js里写入
```js
module.exports = {
  css: {
    loaderOptions: {
      postcss: {
        plugins: [
          require('postcss-pxtorem')({
            rootValue: 19, // 换算的基数(设计图750的根字体为32)
            selectorBlackList: [], // 忽略转换正则匹配项
            propList: ['*'],  //要转换的匹配项
          })
        ]
      }
    }
  }
}
```
### el-input高度宽度等修改
> 另写一个style标签

```html
<style>
    .login_container .el-input__inner{
        height: 60px;
        line-height: 60px;
    }
    .el-input__prefix{
        left: 30px
    }
    .el-input--prefix .el-input__inner{
        padding-left: 80px;
    }
</style>
```