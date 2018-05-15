---
id: form
title: Form
sidebar_label: Form
---

# 使用
```JS
import mobx, { observable, action, transaction, spy } from 'mobx';
const search = observable({
  start: moment().add(-6, 'days').format('YYYY-MM-DD'),
  end: moment().format('YYYY-MM-DD'),
  room: 'all'
});
const noticeRule = observable({
  singlePhone: [
    { required: true, message: '必填'},
    { ...rules.cellphone }
  ]
})
@observer
export default class Remind extends React.Component {
  render() {
    return (
      <Form model={notice} rules={noticeRule} ref={ref => this.remindForm = ref} labelWidth={80} labelPosition=":flex-start">
        <FormItem labelStyle={labelStyle} className="mb-13" label="弹窗提醒">
          <Select_ duplex="alert" style={{ width: 130 }}>
            <Option value={1}>开启</Option>
            <Option value={0}>关闭</Option>
          </Select_>
        </FormItem>
        <FormItem labelStyle={labelStyle} className="mb-13" label="声音提醒">
          <Select_ duplex="voice" style={{ width: 130 }}>
            <Option value={1}>开启</Option>
            <Option value={0}>关闭</Option>
          </Select_>
        </FormItem>
        <FormItem labelStyle={labelStyle} className="mb-13" label="电话提醒">
          <Select_ duplex="phone" style={{ width: 130 }}>
            <Option value={1}>开启</Option>
            <Option value={0}>关闭</Option>
          </Select_>
          {notice.phone === 1 &&
            <View clear mt={20}>
              {phones.map((item, i) => {
                return (
                  <View clear key={i} mb={i === phones.length - 1 ? 0 : 14}>
                    <FormItem prop="singlePhone" duplex={['phones', i]} labelWidth={0}>
                      <Input_ key={i} type_="vice" duplex={['phones', i]} style={{ width: 130 }} placeholder="请输入手机号" />
                    </FormItem>
                  </View>
                )
              })}
            </View>
          }
        </FormItem>
      </Form>
    )
  }
}
```

# 校验规则的使用说明

校验规则的使用分为两步

* 在Form上传入rules={noticeRule} 参见上面代码
* 在FormItem中传入prop="singlePhone"，如果是数组还需要传入duplex，duplex的取值和循环元素的取值一样，循环的元素注意加上key 参见上面代码

# API

> style,className等原有属性均支持

## Form方法

方法 | 说明 | 用法
---|---|---|
resetFields | 重置表单默认值 | this.xxxFrom.resetFields()
resetFieldsStyle| 重置校验过之后的样式 | this.xxxFrom.resetFieldsStyle()
validate| 校验表单，返回一个Promise实例，也支持传入回调函数处理 | this.xxxForm.validate().then((valid)=>{}) 或者 this.xxxForm.validate((valid)=>{})

## Form属性

方法 | 说明 | 类型 | 默认值 | 必须
---|---|---|---|---|
model | mobx的observable对象，存储表单的数据 | object | - | Y
rules | mobx的observable对象或JS对象，验证表单的规则 | object | - | 
inline | form表单的布局方式。设为true时，form的子元素按inline布局 | bool | false |
layout | FormItem整体、Action以及各个FormItem的布局,用法可为‘:flex:block’，未设置的那个值回去默认值
第一个值表示FormItem整体的布局，可取值flex和block
第二个值表示Action的布局，可取值flex和block
第三个值表示各个FormItem的布局，可取值flex和block | string | 'flex:block:block' |
actionPosition | Action的位置，用法可为‘:flex-start’或‘bottom:’，未设置的那个值取默认值
第一个值表示action相对于FormItem的位置，可取值right和bottom
第二个值表示action局部的布局，有效值alignItem的值 | string | 'right:flex-end' |
labelPosition | FormItem中label的位置，用法可为‘::right’，未设置的那个值取默认值
第一个值表示label的宏观位置，取值为top或者left
第二个值表示label在垂直方向的布局，有效值是alignItems的值
第三个是label在水平方向的布局，取值为textAlign的值 | string | 'left:center:right' |
fillCount | 每行FormItem的数量，如果最后一行FormItem数量<fillCount，会使用空的FormItem填充，以保证布局的对齐 | number | 1 |
manualLayout | 手动布局，设为true时，上面的inline,layout,actionPosition,lablePosition,fillCount不再生效 | bool | false |
labelWidth | label的宽度，设为0时，会被替换为'auto' | number | 0 |
needCls | 设为false时，不再使用q-antd自带的样式className——i-form | bool | true |

## FormItem属性

方法 | 说明 | 类型 | 默认值 | 必须
---|---|---|---|---|
label | FormItem各项名称 | string | - | 
labelStyle | label的style | object | - | 
labelWidth | label的宽度 | number | 0 | 
prop | 表单验证时候用到，若无此属性，不验证。取值为Form重rules属性中的key | number | - | 

## Action属性

方法 | 说明 | 类型 | 默认值 | 必须
---|---|---|---|---|
