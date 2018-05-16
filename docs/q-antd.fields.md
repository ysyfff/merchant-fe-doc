---
id: q-antd.fields
title: 各表单元素
sidebar_label: 各表单元素
---

## 特殊说明

* q-antd中的所有表单元素命名规则都是在antd的命名之后加上\_。比如Input在q-antd中就叫Input_;Input.TextArea在q-antd中就叫Input_.TextArea_
* 由于有些antd组件的源码存在缺陷，故做如下特殊说明
  * Mention_双绑的时候有bug，可使用antd的Mention
  * Select_, TreeSelect_双绑的值当且仅当为none(void 0的别名)的时候才显示placeholder

## 使用说明

* 每个元素都有一个duplex属性，此属性与Model或者Form组件的model属性结合起来完成双绑，duplex的值为model对象的key

## 表单元素列表

* Input_、Input_.TextArea_
* InputNumber_
* Radio_、Radio_.Group_
* Checkbox_、Checkbox_.Group_
* Select_
* AutoComplete_
* Cascader_
* DatePicker_、DatePicker_.MonthPicker_、DatePicker_.WeekPicker_、DatePicker_.RangePicker_
* Rate_
* Slider_
* Switch_
* TreeSelect_
* TimePicker_
* Transfer_

## 使用示例

```JS
import React from 'react';
import mobx, { observable, action } from 'mobx';
import { observer, Provider } from 'mobx-react';
import { Radio, Select, TreeSelect } from 'antd';
const { Option } = Select;
const { TreeNode } = TreeSelect;
import {
  Input_,
  InputNumber_,
  Radio_,
  Checkbox_,
  AutoComplete_,
  Cascader_,
  DatePicker_,
  Select_,
  Slider_,
  Switch_,
  TreeSelect_,
  TimePicker_,
  Transfer_,
  // Mention_, //Mention_的双绑有问题，antd的实现有问题
  Rate_,
  Model,
  Form,
  View
} from 'q-antd';
const { MonthPicker_, WeekPicker_, RangePicker_ } = DatePicker_;
const cascaderOptions = [{
  value: 'zhejiang',
  label: 'Zhejiang',
  children: [{
    value: 'hangzhou',
    label: 'Hangzhou',
    children: [{
      value: 'xihu',
      label: 'West Lake'
    }]
  }]
}, {
  value: 'jiangsu',
  label: 'Jiangsu',
  children: [{
    value: 'nanjing',
    label: 'Nanjing',
    children: [{
      value: 'zhonghuamen',
      label: 'Zhong Hua Men'
    }]
  }]
}];
const mockData = [];
for (let i = 0; i < 20; i++) {
  mockData.push({
    key: i.toString(),
    title: `content${i}`,
    description: `description of content${i}`,
    disabled: i % 3 < 1
  });
}
const targetKeys = mockData
  .filter(item => +item.key % 3 > 1)
  .map(item => item.key);
const search = observable({
  a: 1,
  aa: '我是TextArea',
  aaa: 1,
  b: true,
  c: '1',
  cc: 'Apple',
  d: true,
  e: ['Apple'],
  suggest: '',
  area: [],
  date: '2014-07-02',
  month: '2014-07-02',
  week: '2014-07-02',
  rangeStart: '2017-10-11',
  rangeEnd: '2018-01-10',
  inputNumber: 8,
  mention: '@afc163 ',
  rate: 1,
  radioGroup: 'Apple',
  radio: false,
  select: none,
  slider: 68,
  sliderRange: [10, 50],
  switch: true,
  treeSelect: none,
  time: '00:00:00',
  transfer: ['2', '5', '8']
});
@observer
export default class QAntd extends React.Component {
  render() {
    return (
      <Model model={search}>
        <View ml={30} mr={30}>
          <div>{JSON.stringify(mobx.toJS(search))}</div><br />
          
          <View clear block><Input_ duplex="a" placeholder="没有form的表单" /></View> Input_的使用<br />
          
          <View clear block><Input_.TextArea_ duplex="aa" rows={2} placeholder="没有form的表单" /></View> Input_.TextArea_的使用<br />
          
          <View clear block><InputNumber_ duplex="aaa" rows={2} placeholder="没有form的表单" /></View> InputNumber_的使用<br />
          
          <Radio_ duplex="b" >我是一个人</Radio_>Radio_的使用，单个Radio可将b设为true或者false <br />
          
          <Radio_.Group_ duplex="c">
            <Radio value="1">1</Radio>
            <Radio value="2">2</Radio>
          </Radio_.Group_> Radio_.Group_的使用之用法一<br />
          
          <Radio_.Group_ duplex="cc" options={[
            { label: 'Apple', value: 'Apple' },
            { label: 'Pear', value: 'Pear' },
            { label: 'Orange', value: 'Orange' }
          ]} /> Radio_.Group_的使用之用法二<br />
          
          <Checkbox_ duplex="d">Banana</Checkbox_> Checkbox_的使用<br />
          
          <Checkbox_.Group_ options={[{ label: 'Apple', value: 'Apple' }, { label: 'Pear', value: 'Pear' }]} duplex="e" /> Checkbox_.Group_的使用<br />
          
          <Select_ style={{ width: 400 }} duplex="select" placeholder="select的双绑值为none的时候才能显示placeholder" >
            <Option value="Jack">Jack</Option>
            <Option value="ruler">ruler</Option>
          </Select_> Select_的使用<br />
          
          <AutoComplete_ duplex="suggest" dataSource={['1', '2', '3']}></AutoComplete_> AutoComplete_的使用 <br />
          
          <Cascader_ style={{ width: 400 }} duplex="area" options={cascaderOptions}></Cascader_> Cascader_的使用 <br />
          
          <DatePicker_ duplex="date" /> DatePicker_的使用 <br />
          
          <MonthPicker_ duplex="month" /> MonthPicker_的使用<br />
          
          <WeekPicker_ duplex="week" /> WeekPicker_的使用<br />
          
          <RangePicker_ duplex="rangeStart, rangeEnd" /> RangePicker_的使用 <br />
          
          <Rate_ duplex="rate" /> Rate_的使用<br />
          
          <Slider_ duplex="slider" min={0} max={100} /> Slider_的使用<br />
          
          <Slider_ range duplex="sliderRange" min={0} max={100} /> Slider_中range的使用<br />
          
          <Switch_ range duplex="switch" min={0} max={100} /> Switch_的使用<br />
          
          <TreeSelect_ treeDefaultExpandAll duplex="treeSelect" placeholder="Please select" >
            <TreeNode value="parent 1" title="parent 1" key="0-1">
              <TreeNode value="parent 1-0" title="parent 1-0" key="0-1-1">
                <TreeNode value="leaf1" title="my leaf" key="random" />
                <TreeNode value="leaf2" title="your leaf" key="random1" />
              </TreeNode>
              <TreeNode value="parent 1-1" title="parent 1-1" key="random2">
                <TreeNode value="sss" title={<b style={{ color: '#08c' }}>sss</b>} key="random3" />
              </TreeNode>
            </TreeNode>
          </TreeSelect_> TreeSelect_的使用<br />
          
          <TimePicker_ duplex="time" /> TimePicker_的使用<br />
          
          <Transfer_
            dataSource={mockData}
            duplex="transfer"
          /> Transfer_的使用<br />
        </View>
      </Model>
    )
  }
}
```

