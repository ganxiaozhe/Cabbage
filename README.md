# Cabbage.js
🥬 Cabbage.js is a beautiful, elegant and convenient JavaScript plugin.

[https://gquery.net/plugins/cabbage](https://gquery.net/plugins/cabbage)

This plugin has been developed by Ganxiaozhe, which is more beautiful and easier to use than other custom right-click menu.
You can do menu binding on any element, and don't worry, it won't cause a conflict.

Cabbage.js rely on gQuery v1.4.2 and above version, the current version only supports secondary submenu.

# Usage
```javascript
$(function(){
    $('#ibanner').cabbage([
        {text:'Cabbage.gQuery.js', func:function(){
            gxz.alert({title:'Cabbage.gQuery.js',message:'多吃蔬菜🥬！！！'});
        }},{break:true},
        {text:'查询 "[:sel]"', selection:true},{text:'卷心菜单',data:[
            {text:'挺好吃'},{text:'不好吃'},{text:'没吃过'}
        ]},
        {text:'重新加载', func:function(){window.location.reload();}},
        {text:'检查', func:function(){
            console.log('当前元素:', this);
        }},{break:true},{text:'gQuery Awesome', disable:true}
    ]);
});
```
After binding the menu, you can delete, add, or change the entire menu or an option at any time.
```javascript
$('#ibanner')[0].gQueryData.cabbageMenu[7] = {
    text:'gQuery Awesome', disable:false, data:[{text:'1', func:function(){alert(0);}},{text:'0'},{text:'1'}]
};
```

# License
[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2020-present, JU Chengren (Ganxiaozhe)
