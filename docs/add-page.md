---
id: add-page
title: 添加新的页面
sidebar_label: 概述
---

common的component中开发了root和layout组件，在页面的index.js中做如下操作即可

## index.js文件示例
```JS
import { Render } from 'component'; //Render函数使用了root和layout组件，方便调用
import App from './notice'; //业务代码
import 'style';
import './api';

Render(App, true); //第二个参数表示是否使用layout组件， 若为false，不展示layout相关的内容

if(module.hot){ //hot reload相关代码
  module.hot.accept();
}
```