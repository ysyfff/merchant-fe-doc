---
id: q-antd
title: q-antd
sidebar_label: q-antd
---

表单元素以及表单校验使用了q-antd

## 简介

q-antd是在antd的基础上，结合mobx，对antd中的表单元素进行二次改装和对Form的重写一个npm包，使得表单元素支持双工绑定，使得表单使用更简单，从而提高开发效率

q-antd的优势是
* 各个表单元素是双绑的，不需要调用onChange函数手动处理变化后的赋值操作
* q-antd的form在使用上比antd的form简单很多，而且form内置了不少自定义布局，能满足绝大数情况下的布局，实在满足不了，可使用manualLayout=true，自定义布局

## 安装使用

> 安装之前需要项目中已经安装了antd

`yarn add q-antd`

## 关于Form

[参见Form](form.md)

## 关于各表单元素

[参见各表单元素用法](fields.md)



