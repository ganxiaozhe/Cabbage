# Cabbage.js
🥬 Cabbage.js is a beautiful, elegant and convenient JavaScript plugin.

[https://gquery.net/plugins/cabbage](https://gquery.net/plugins/cabbage)

该插件由 Ganxiaozhe 开发，相比其他自定义右键菜单，卷心菜单更美观，且更易于使用。同时，支持无限套娃！你可以对任意元素进行菜单绑定，放心，这并不会造成冲突。

Cabbage.js 依赖 gQuery v1.4.2 及以上版本。

# 简介
```javascript
$(function(){
    $('#ibanner').cabbage([
        {text:'Cabbage.gQuery.js', func:function(){
            gxz.alert({title:'Cabbage.gQuery.js',message:'多吃蔬菜🥬！！！'});
        }},{break:true},
        {text:'查询 "[:sel]"', selection:true, func:function(opts){
            window.open("https://www.baidu.com/s?ie=UTF-8&wd="+opts.selText, "blank");
        }},
        {text:'卷心菜单',data:[
            {text:'挺好吃'},{text:'不好吃'},
            {text:'没吃过', data:[
                {text:'真的假的', disable:true},{break:true},{text:'真的', data:[
                    {text:'???'}
                ]},{text:'假的'}
            ]}
        ]},
        {text:'重新加载', func:function(){window.location.reload();}},
        {text:'检查', func:function(){
            console.log('当前元素:', this);
        }},{break:true},{text:'gQuery Awesome', disable:true}
    ]);
});
```
绑定菜单后，你可以随时删、增、改整个菜单或某个选项内容：
```javascript
$('#ibanner')[0].gQueryData.cabbageMenu[7] = {
    text:'gQuery Awesome', disable:false, data:[{text:'1', func:function(){alert(0);}},{text:'0'},{text:'1'}]
};
```

# 安装
你需要引入以下文件：（请勿在开发环境下使用压缩版本，否则将失去错误相关警告!）
```html
<link type="text/css" rel="stylesheet" href="cabbage.gquery.css">

<script type="text/javascript" src="gquery.min.js"></script>
<script type="text/javascript" src="cabbage.gquery.min.js"></script>
```

# 使用
Cabbage.js 通过 `$.fn.extend` 将其方法拓展进 gQuery 原型链，你可以直接通过 gQuery 选择器对单个或多个元素进行绑定。当要为全局进行菜单绑定时，请使用 `$('body')` 而非 `$(window)` 或 `$(document)`。

Cabbage.js 的配置肥肠直观，一个菜单即为一个数组对象，一个对象即为一个菜单选项。一个最简单的菜单可以是：`[{text:'Cabbage.gQuery.js'}]`，啊不对，应该是 `[]`。

没错，卷心菜也有奇淫巧技，可以传入一个空数组以屏蔽浏览器默认右键，其完整代码为：`$('body').cabbage([]);`

一个菜单选项有以下对象可选：

```javascript
{
    // 显示的名字
    text: '大白菜，人人爱',

    // 为分割线
    break: true,
    // 不可点击
    disable: true,
    // 当选中内容后右键，此项才会被显示
    selection: true

    // 点击此项执行的函数
    func: function(){...},
}
```
其中 text 支持特殊字符组合以变为相应变量，例如 [:sel] 在菜单项中将变为右键时选中的内容...


# License
[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2020-present, JU Chengren (Ganxiaozhe)
