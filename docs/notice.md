---
id: notice
title: 开发须知
sidebar_label: 概述
---


## 工程结构

工程使用了[packing](https://github.com/packingjs/packing)构建，选用react + antd + q-antd + mobx进行开发

## 目录与路径

根据模块以及功能划分目录结构，目录结构==url路径。例如在entries里面的目录结构为speaker/notice，访问此页面的路径也是speaker/notice

## 组件

绝大数使用了antd的组件，不满足需求的时候进行了二次封装，为了保证整站风格统一，有封装组件要使用封装组件。

### 封装组件列表

* Pagination_

## 样式

组件样式开发在`common/style`文件夹里面，根据需要按照antd的目录结构以及各组件的less结构进行样式的覆盖

## 校验规则

通用Form校验正则以及校验规则，统一放在`common/util/rules`里面

