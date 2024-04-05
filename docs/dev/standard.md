# 插件规范

> 在开始构建你的插件之前，你可能需要了解DynlantRD插件规范。

1. 插件必须携带的信息
- name:好在一群插件中识别你的插件
- type:指定类型，用于区分"render"和"ornament"
- protocol:插件注册协议，提供向下兼容用
- > 当前的protocol版本为1
- node:提供辨识，Render选择插件的主要依据
- exec:插件主程序

这是一个简单的实例:
- 第一种写法(不推荐)
```javascript
const plugin = {
  name:'sss',
  protocol:1,
  type:'render',
  node:'RICH_TEXT_NODE_TEXT',
  exec:function(param,processor){
    let text = param.orig_text;
    let processors_object={
      element:'p',
      text:text,
      attribute:
        {
          style:"display: inline;margin:0;"
        }
    };
    return obj;
  }};

dynlantrd.RegisterPlugin(plugin);
```
- 第二种写法(推荐)
```javascript
const plugin = {
  name:'sss',
  protocol:1,
  type:'render',
  node:'RICH_TEXT_NODE_TEXT',
  exec:function(param,processor){
    
    return obj;
  }};

dynlantrd.RegisterPlugin(plugin);
```