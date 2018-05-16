---
id: q-antd.view
title: View
sidebar_label: View
---

对div标签的升级，支持属性定义样式

## 示例

```JS
export default class Demo extends React.Component{
  render(){
    return(
      <View ml={20} mr={20} paddingTop={10} borderWidth={2} block clear>
        xxx
      </View>
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
View类型，有效值为oneOf([hp-20,hp-30,vp-20,vp-30])
类型 | 默认值
---|---
string|hp-20

### block
View表现为inline-block
类型 | 默认值
---|---
bool|false

### clear
取消type的默认值
类型 | 默认值
---|---
bool|false