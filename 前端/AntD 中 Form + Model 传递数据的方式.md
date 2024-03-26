# 场景
点击打开 Model 弹窗，弹窗中包含 Form 表单。在弹窗内修改值后将值传递给父组件

# 方法

> 常规方法

**Form 包含 Button**
为 Button 添加 htmlType="submit" 属性，点击 Button 将触发 Form 表单的 onFinish 事件

**Form 不包含 Button**
为 Form 设置 Id，Button 添加 form="form 中的 id" 属性，点击 Button 依旧会触发 Form 表单的 onFinish 事件

> 操作 Form 表单示例

使用 `const [form] = Form.useForm()` 获取表单实例，赋给 Form 标签中的 form 属性
- 通过 `form.getFieldValue()` 获取表单值
- 通过 `form.submit()` 提交表单，触发 Form 的 onFinish 事件

``` jsx
const [form] = Form.useForm();

  const Button = () => (
    <div style={{ textAlign: 'right' }}>
      <Button type="primary" onClick={form.submit}>
        提交
      </Button>
    </div>
  )
  
  <Form
    form={form}
    onFinish={(values) => {console.log(values)}}
  >
  
  </Form>
 
```