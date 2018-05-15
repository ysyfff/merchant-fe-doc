---
id: ajax
title: 接口调用
sidebar_label: 概述
---

在`common/util`的ajax中封装了packingjs，统一处理了错误，增加了mock等，并将其挂载到Q命名空间上方便调用

## 使用步骤

* 每个页面中新建一个api.js，此页面的所有请求都通过Q.ajax.setup在此配置
* 在业务页面引入api.js，通过Q.ajax(AJAX_NAME, param)来调用

## 示例

假如目录结构如下
```JS
+--notice
|----api.js
|----app.js
|----index.js
```

notice/api.js代码如下
```JS
Q.ajax.setup(false, {
  FETCH_LIST: {
    url: 'xxxx',
    ajaxType: Q.ajaxType.GET,
    tip: false,
    mock: {
      ret: true,
      msg: '',
      data: {
        total: 100,
        list: [{
          id: 1
        }]
      }
    }
  }
})
```

notice/app.js代码如下
```JS
Q.ajax('FETCH_LIST', {seq: 'xxx'}).then((res)=>{
  //业务代码
})
```

## Q.ajax.setup配置属性
> 以下只展示了自定义封装属性以及部分ajax属性，其他属性参考[jquery的ajax配置](http://api.jquery.com/jquery.ajax/)
<!-- 
- [url](interface.md#url)
- [ajaxType](interface.md#ajaxtype)
- [tip](interface.md#tip)
- [loading](interface.md#loading)
- [mock](interface.md#mock)
- [preprocess](interface.md#preprocess)
- [lock](interface.md#lock)
- [succMsg](interface.md#succmsg)
- [failMsg](interface.md#failmsg) -->


### `url`
请求路径
type|default
---|---
string | -

### `ajaxType`
请求type
type|default
---|---
object | Q.ajaxType.GET


### `tip`
是否展示消息
type|default
---|---
string | true

### `loading`
是否全局展示加载中cover
type|default
---|---
bool | false

### `mock`
mock数据对象
type|default
---|---
Object|Array | -

### `preprocess`
预处理函数
 type|default
---|---
function | -

### `lock`
锁定，锁定之后在同一个请求返回之前不会发送第二次请求
 type|default
---|---
bool | true


### `succMsg`
成功消息
type|default
---|---
string | -

### `failMsg`
失败消息
type|default
---|---
string | -



