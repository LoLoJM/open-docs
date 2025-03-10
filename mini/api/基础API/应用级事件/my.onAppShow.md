
# 简介
**my.onAppShow** 是监听小程序切前台事件的 API。该事件与框架 [app.js 注册小程序](https://opendocs.alipay.com/mini/framework/app-detail) 时 onShow 参数的回调时机一致。对应的取消监听 API 请参见 [my.offAppShow](api/tkohmw)。

## 使用限制

- 基础库 [1.20.0](https://opendocs.alipay.com/mini/framework/lib) 或更高版本；支付宝客户端 10.1.68 或更高版本，若版本较低，建议采取 [兼容处理](/mini/framework/compatibility)。<br />
- 由于开发者工具版本限制，目前本 API 暂不支持在开发者工具调试和真机调试，仅支持真机预览。开发者请调至 **预览** 模式，在支付宝客户端扫码查看效果。<br />
- 请勿使用 API 监听匿名函数，否则将无法关闭监听。
- 此 API 支持个人支付宝小程序、企业支付宝小程序使用。

# 接口调用

## 示例代码

### .axml 示例代码
```html
<!-- .axml-->
<button size="default" onTap="offAppShowHanlder" type="primary">关闭监听到前台</button>
```

### .js 示例代码
```javascript
//.js
onLoad() {
    my.onAppShow(this.onAppShowHandler)
},
//监听切换到前台方法
onAppShowHandler() {
    console.log('前台了，到了')
},
//取消监听切换到前台方法
offAppShowHanlder() {
    my.offAppShow(this.onAppShowHandler)
},
apphide() {
    console.log('监听后台加载成功')
}
```

## 入参
入参为 Object 类型，属性如下：

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| callback | Function | 小程序切前台事件的回调函数。回调函数的参数请参考框架 [app.js 注册小程序](https://opendocs.alipay.com/mini/framework/app-detail) 时 onShow 的回调参数。 |

