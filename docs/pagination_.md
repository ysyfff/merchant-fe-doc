---
id: pagination_
title: Pagination_
sidebar_label: Pagination_
---

根据UI图定制化Pagination，用法和Pagination基本一样

## 使用

```JS
<Pagination_ 
  defaultCurrent={1} 
  current={search.page} 
  onJump={page => search.page = page} 
  total={listData.totalCount} 
  onChange={this.handlePageChange}
/>
```

## Props
> 只展示了Pagination_特有的属性或方法，其他的继承antd的Pagination

- [`onJump`](pagination_.md#onjump)
- [`showJumper`](pagination_.md#showjumper)

### `onJump`
(jumpTo)=>{}

跳至回调，传入跳至的页码数

类型 | 必需
--- | ---
function | false

### `showJumper`

展示共多少也，和跳至相关内容

类型 | 必需
--- | ---
bool | false


