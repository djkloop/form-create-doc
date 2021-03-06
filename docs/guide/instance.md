---
sidebarDepth: 3

---

# 实例方法

::: warning 注意

1.4.1版本之后 `model`方法无需传参, 使用方法 `form = $f.model()`。

:::

## $f.fields

- **用法**：

  ```js
  $f.fields()
  ```

  获取表单所有字段名


## $f.formData

- **用法**：

  ```js
  formData = $f.formData()
  ```

  获取表单的键值对


## $f.getValue

- **参数**：`{string} field`

- **用法**：

  ```js
  field_value = $f.getValue(field)
  ```

   获取指定字段的值



## $f.changeField

- **参数**：`{string} field`、`value`

- **用法**：

  ```js
  $f.changeField(field,value)
  ```

  修改指定字段的值



## $f.resetFields

- **用法**：

  ```js
  $f.resetFields()
  ```

  重置表单


## $f.removeField

- **参数**：`{string} field`

- **用法**：

  ```js
  $f.removeField(field)
  ```

  删除指定字段



## $f.model

- **用法**：

  ```js
  model = $f.model()
  ```

- **数据结构**：

  ```js
  {
      field1:{value,rule:{props,validate,options,slot,event,...[其他配置项]}}
      field2:{value,rule:{props,validate,options,slot,event,...[其他配置项]}}
  }
  ```

  获取双向数据绑定的表单生成规则


## $f.bind 

- **用法**：**`>=1.4.1版本`**

  ```js
  bind = $f.bind()
  ```

  获取双向数据绑定的表单键值对


## $f.hidden

- **参数**：`{string} field`、`{bool} hidden`

- **用法**：**`>=1.4.1版本`**

  ```js
  $f.hidden(field,true)
  ```

  隐藏或显示指定组件


## $f.visibility 

- **参数**：`{string} field`、`{bool} visibility`

- **用法**：**`>=1.4.1版本`**

  ```js
  $f.visibility(field,true)
  ```

  隐藏或显示指定组件


## $f.validate

- **参数**：`{function} success`、`{function} error`

- **用法**：

  ```js
  $f.validate(()=>console.log('验证通过'),()=>console.log('验证未通过'))
  ```

  表单验证,如果验证通过执行`success`,未通过则执行`error`


## $f.validateField

- **参数**：`{string} field`、`{function} callback`

- **用法**：

  ```js
  $f.validateField(field,(errMsg)=>{
      if(errMsg){
          //TODO 验证未通过
      }else{
          //TODO 验证通过
      }
  });
  ```

  表单验证指定字段


## $f.prepend

::: warning 建议

建议直接操作生成规则`rules`，插入到数组对应的位置即可

:::

- **参数**：`{object} rule`、`{stirng} field`

- **用法**：

  ```js
  $f.prepend({
         type:"input",
         title:"商品简介",
         field:"goods_info",
         value:"",
         props: {
             "type": "text",
             "placeholder": "请输入商品简介",
         },
         validate:[
             { required: true, message: '请输入商品简介', trigger: 'blur' },
         ],
  },undefined);
  ```

  在`field`的字段之前插入指定表单元素,不传入`field`默认在第一个


## $f.append

::: warning 建议

建议直接操作生成规则`rules`，插入到数组对应的位置即可

:::

- **参数**：`{object} rule`、`{stirng} field`

- **用法**：

  ```js
  $f.prepend({
         type:"input",
         title:"商品简介",
         field:"goods_info",
         value:"",
         props: {
             "type": "text",
             "placeholder": "请输入商品简介",
         },
         validate:[
             { required: true, message: '请输入商品简介', trigger: 'blur' },
         ],
  },null);
  ```

  在`field`的字段之后插入指定表单元素,不传入`field`默认在最后一个


## $f.submitStatus

- **参数**：`{object} props`

- **用法**：

  ```js
  $f.submitStatus({loading:true})
  ```

- **快捷操作**:

  - `$f.btn.loading(loading = true)` 设置提交按钮进入loading状态
  - `$f.btn.disabled(disabled = true)` 设置提交按钮禁用状态

- **props**：

  ```js
  {
          //按钮类型，可选值为primary、ghost、dashed、text、info、success、warning、error或者不设置
          type:"primary",
          //按钮大小，可选值为large、small、default或者不设置
          size:"large",
          //按钮形状，可选值为circle或者不设置
          shape:undefined,
          //开启后，按钮的长度为 100%
          long:true,
          //设置button原生的type，可选值为button、submit、reset
          htmlType:"button",
          //设置按钮为禁用状态
          disabled:false,
          //设置按钮的图标类型
          icon:"ios-upload",
          //按钮文字提示
          innerText:"提交",
          //设置按钮为加载中状态
          loading:false
  }
  ```

  修改表单提交按钮规则


## $f.resetStatus

- **参数**：`{object} props`

- **用法**：

  ```js
  $f.resetStatus({disabled:true})
  ```

- **快捷操作**:

  - `$f.resetBtn.loading(loading = true)` 设置重置按钮进入loading状态
  - `$f.resetBtn.disabled(disabled = true)` 设置重置按钮禁用状态

- **props**：

  ```js
  {
          //按钮类型，可选值为primary、ghost、dashed、text、info、success、warning、error或者不设置
          type:"primary",
          //按钮大小，可选值为large、small、default或者不设置
          size:"large",
          //按钮形状，可选值为circle或者不设置
          shape:undefined,
          //开启后，按钮的长度为 100%
          long:true,
          //设置button原生的type，可选值为button、submit、reset
          htmlType:"button",
          //设置按钮为禁用状态
          disabled:false,
          //设置按钮的图标类型
          icon:"ios-upload",
          //按钮文字提示
          innerText:"提交",
          //设置按钮为加载中状态
          loading:false
  }
  ```

  修改表单重置按钮规则


## $f.submit

- **参数**：`{function} onSubmit`

- **用法**：

  ```js
  $f.submit((formData)=>{
      //提交表单
  })
  ```

  手动提交表单,如果传入`onSubmit`参数,就不会再触发`option.onSubmit`


## $f.options

- **参数**：`{object} options`

- **用法**：

  ```js
  $f.options(({
      onSubmit:(formData)=>{
          //提交表单
      }
  })
  ```

  更新全局配置

- **参考**：[全局配置](http://www.form-create.com/guide/global.html)



## $f.reload

- **参数**：`{array} rules`

- **用法**：

  ```js
  $f.reload()
  ```

  按照新的生成规则重载表单生成器,如果不传入`rules`会按照当前规则重载


## $f.refresh

- **用法**：

  ```js
  $f.refresh()
  ```

  重新渲染表单


## $f.sync

- **参数**：`{string} field`

- **用法**：

  ```js
  $f.sync(field)
  ```

  重新渲染`field`组件


## $f.destroy

- **用法**：

  ```js
  $f.destroy()
  ```

  销毁表单


## $f.set

- **参数**：`{object} node`、`{string} key`、`value`

- **用法**：

  ```js
  $f.set(field.rule.col,'span',12)
  ```

  如果修改组件的规则后页面没有更新时可以尝试使用该方法,该方法使用方法与`Vue.$set`相同


## $f.closeModal

- **用法**：

  ```js
  $f.closeModal()
  ```

  关闭frame组件的弹出框



