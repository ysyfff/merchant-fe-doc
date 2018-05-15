---
id: notice
title: 开发须知
sidebar_label: 概述
---

## 须知列表

- 工程使用了packing构建，选用react + antd + q-antd + mobx进行开发
- 根据模块以及功能划分目录结构，目录结构==url路径。例如在entries里面的目录结构为speaker/notice，访问此页面的路径也是speaker/notice
- 分页要使用Pagination_组件, 此组件根据UI的图对antd的Pagnination进行了改进
- 组件样式开发在`common/style`文件夹里面，根据需要按照antd的目录结构以及各组件的less结构进行样式的覆盖
- 通用Form校验正则以及校验规则，统一放在`common/util/rules`里面

