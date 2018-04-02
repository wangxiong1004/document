## layer

官网

    [http://layer.layui.com/](http://layer.layui.com/)

---

#### 模块化使用
```
    layui.use('layer', function(){
        var layer = layui.layer;
    
        layer.msg('hello');
    });  
```

--- 

#### 常用参数

- 类型: type - Number
```
    type: 0（信息框，默认）1（页面层）2（iframe层）3（加载层）4（tips层）

    layer.open({
        type: 0
    });
```

- 标题: title - String/Array/Boolean
```
    title: false    // 不显示标题

    title: "标题内容"   // 标题内容

    title: ["标题内容", "font-size: 18px;"]     // 标题内容 + 样式

```

- 内容: content - String/DOM/Array
```
    // type: 1 -- 页面层
    content: '传入任意的文本或html'

    content: $('#id') // 这里content是一个DOM，注意：最好该元素要存放在body最外层，否则可能被其它的相对元素所影响

    // Ajax获取
    content: str // 注意，如果str是object，那么需要字符拼接。

    // type: 2 -- iframe层
    content: 'http://sentsin.com' // 这里content是一个URL，如果你不想让iframe出现滚动条，你还可以content: ['http://sentsin.com', 'no']

    // type: 4 -- tips层
    content: ['内容', '#id'] // 数组第二项即吸附元素选择器或者DOM
```

- 自定义class: skin - String
```
    // 单个配置
    skin: 'demo-class'

    // 全局配置--即所有弹出层都默认采用，但是单个配置skin的优先级更高
    layer.config({
        skin: 'demo-class'
    })
```

- 自定义宽高: area - String/Array
```
    area: 'auto'    // 默认

    area: '500px'   // 宽度固定,高度自适应
    
    area: ['500px', '600px']    // 宽度固定,高度固定
```

- 按钮: btn - String/Array
> 信息框模式时，btn默认是一个确认按钮，其它层类型则默认不显示，加载层和tips层则无效。
```
    btn: '确认'     // 一个按钮
    yes: function() {}  // 回调

    btn: ['按钮1', '按钮2', '按钮...']  // 2个及以上按钮
    yes: function(index, layero) {},
    btn2: function(index, layero) {},
    btn...: function(index, layero) {}
      
```

- 按钮排列: btnAlign - String
> btnAlign的默认值为r，即右对齐
```
    btnAlign: 'l'   // 按钮左对齐

    btnAlign: 'c'   // 按钮居中对齐

    btnAlign: 'r'   // 按钮右对齐。默认值，不用设置
```

- 关闭按钮: closeBtn - String/Boolean
```
    closeBtn: 0     // 不显示
    
    closeBtn: 1     // 风格1

    closeBtn: 2     // 风格2

    cancel: function() {    // 右上角关闭按钮回调
        //return false 开启该代码可禁止点击该按钮关闭
    } 
```

- 遮罩: shade - String/Array/Boolean
> 默认是0.3透明度的黑色背景（'#000'）
```
    shade: 0    // 不显示遮罩

    shade: [0.8, '#000']    // 配置
```

- 是否点击遮罩关闭: shadeClose - Boolean
```
    shadeClose: false   // 默认

    shadeClose: true   
```

- 自动关闭所需毫秒: time - Number
> 默认不会自动关闭。当你想自动关闭时，可以time: 5000，即代表5秒后自动关闭，注意单位是毫秒（1秒=1000毫秒）
```
    time: 5000
```

- 用于控制弹层唯一标识: id - String
> 设置该值后，不管是什么类型的层，都只允许同时弹出一个。一般用于页面层和iframe层模式
```
    id: 'test'
```

- 弹出动画: anim - Number
> 兼容: ie9+
```
    anim: -1    // 不显示动画

    anim: 0	    // 平滑放大。默认

    anim: 1	    // 从上掉落

    anim: 2	    // 从最底部往上滑入

    anim: 3	    // 从左滑入

    anim: 4	    // 从左翻滚

    anim: 5	    // 渐显

    anim: 6	    // 抖动
```

- 关闭动画: isOutAnim - Boolean
> 关闭层时的过度动画
```
    isOutAnim: false    // 不开启关闭动画
```

- 固定: fixed - Boolean
> 鼠标滚动时，层是否固定在可视区域
```
    fixed: false    // 不固定
```

- 是否允许拉伸: resize - Boolean
> 默认情况下，你可以在弹层右下角拖动来拉伸尺寸.该参数对loading、tips层无效
``` 
    resize: false   // 不允许拉伸

    // 监听窗口拉伸动作
    resizing: function(layero) {
        
    }
```