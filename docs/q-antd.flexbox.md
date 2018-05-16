---
id: q-antd.flexbox
title: Flexbox
sidebar_label: Flexbox
---

对flex布局的简单封装，需要Flexbox, Flex, Block三个组件一起使用

## 示例

```JS
import {Flexbox} from 'q-antd'
const {Flex, Block} = Flexbox;

export default class Demo extends React.Component {
  render() {
    return (
      <Flexbox>
        <Flex flex={3}>
          什么是服务器端渲染(SSR)？<br/>
          Vue.js 是构建客户端应用程序的框架。默认情况下，可以在浏览器中输出 Vue 组件，进行生成 DOM 和操作 DOM。然而，也可以将同一个组件渲染为服务器端的 HTML 字符串，将它们直接发送到浏览器，最后将静态标记"混合"为客户端上完全交互的应用程序。<br/>

          服务器渲染的 Vue.js 应用程序也可以被认为是"同构"或"通用"，因为应用程序的大部分代码都可以在服务器和客户端上运行。
        </Flex>
        <Flex>
          这么牛
        </Flex>
        <Block>
          OK
        </Block>
      </Flexbox>
    )
  }
}
```

## Flexbox属性

> 除了以下属性，也支持style属性

### alignItems
同style的alignItems

类型 | 默认值
---|---
string| -

### jusitfyContent
同style的jusitfyContent

类型 | 默认值
---|---
string| -

### flexDirection
同style的flexDirection

类型 | 默认值
---|---
string| -

## Flex属性

### flex
同style的flex

类型 | 默认值
---|---
number| 1

## Block属性