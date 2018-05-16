---
id: q-antd.text
title: Text
sidebar_label: Text
---

文字标签

## 示例

```JS
export default class Demo extends React.Component{
  render(){
    return(
      <Text size="small" type="dark" bold italic ml={20}>
        提交
      </Text>
    )
  }
}
```

## Props

> 除了以下属性，同时支持style属性以及具体的style的属性

### ml
margin-left缩写
类型 | 默认值
---|---
number|-

### mr
maring-right缩写
类型 | 默认值
---|---
number|-

### pl
padding-left缩写
类型 | 默认值
---|---
number|-

### pr
padding-right缩写
类型 | 默认值
---|---
number|-

### type
Text类型，有效值为
* normal
* dark
* primary
* primary-deep
* warning
* error
* success
* room-number
* remark
* main

类型 | 默认值
---|---
string|normal

### size
字体大小，有有效值为
* small
* normal
* large

类型 | 默认值
---|---
string|normal


### bold
是否为粗体

类型 | 默认值
---|---
bool|false

### italic
是否为斜体

类型 | 默认值
---|---
bool|false



