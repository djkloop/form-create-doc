### Slider 滑块

#### [在线预览](https://jsrun.net/rehKp/edit)

#### 举例:
```js
{
        type:"slider",
        field:"slider",
        title:"滑块",
        value:[0,52],
        props:{
            "min": 0,
            "max": 100,
            "range": true,
        }
}
```

#### maker快速生成:
```js
$formCreate.maker.slider('滑块','slider',[0,52]).props({
        "min": 0,
        "max": 100,
        "range": true,
        "showTip":"always"
})
```

#### json 生成规则
```json
{
     type:"slider",
     field:"slider",
     title:"滑块",
     value:[0,50], //滑块选定的值。普通模式下，数据格式为数字，在双滑块模式下，数据格式为长度是2的数组，且每项都为数字
     props:{
          "min": 0, //最小值
         "max": 100, //最大值
         "step": 1, //步长，取值建议能被（max - min）整除
         "disabled": false, //是否禁用滑块
         "range": true, //是否开启双滑块模式
         "showInput":false, //是否显示数字输入框，仅在单滑块模式下有效
         "showStops":true, //是否显示间断点，建议在 step 不密集时使用
          "showTip":"hover", //提示的显示控制，可选值为 hover（悬停，默认）、always（总是可见）、never（不可见）
         "tipFormat":undefined, //Slider 会把当前值传给 tip-format，并在 Tooltip 中显示 tip-format 的返回值，若为 null，则隐藏 Tooltip
         "inputSize":"small", //数字输入框的尺寸，可选值为large、small、default或者不填，仅在开启 show-input 时有效
     },
     validate:[]
}
```

#### 参数说明
##### 基本规则 rule:

| 字段名 | 说明 | 字段类型 | 是否必填 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| type | 元素类型 | String | true | - |
| field | 字段名称 | String | true | - |
| title | 字段别名 | String | true | - |
| value | 滑块选定的值。普通模式下，数据格式为数字，在双滑块模式下，数据格式为长度是2的数组，且每项都为数字 | Number ,Array | false | - |
| props | 元素配置 | Object | false | - |
| event | 元素事件 | Object | false | - |
| validate | 验证规则 | Array | false | - |

##### 元素配置 props:

| 字段名 | 说明 | 字段类型 | 是否必填 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| min | 最小值 | Number | false | 0 |
| max | 最大值 | Number | false | 100 |
| step | 步长，取值建议能被（max - min）整除 | Number | false | 1 |
| disabled | 是否禁用滑块 | Boolean | false | false |
| range | 是否开启双滑块模式 | Boolean | false | false |
| showInput | 是否显示数字输入框，仅在单滑块模式下有效 | Boolean | false | false |
| showStops | 是否显示间断点，建议在 step 不密集时使用 | Boolean | false | false |
| showTip | 提示的显示控制，可选值为 hover（悬停，默认）、always（总是可见）、never（不可见） | String | false | 'hover' |
| tipFormat | Slider 会把当前值传给 tip-format，并在 Tooltip 中显示 tip-format 的返回值，若为 null，则隐藏 Tooltip | Function | false | - |
| inputSize | 数字输入框的尺寸，可选值为large、small、default或者不填，仅在开启 show-input 时有效 | String | false | 'default' |

##### 事件扩展 event:

| 事件名称 | 说明 | 字段类型 | 是否必填 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| change | 在松开滑动时触发，返回当前的选值，在滑动过程中不会触发 | Function | false | - |
| input | 滑动条数据变化时触发，返回当前的选值，在滑动过程中实时触发 | Function | false | - |

---



