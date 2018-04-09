## css3

- link
```
    <link rel="stylesheet" type="text/css" href="*.css"></link>
```

- @import
> 用于在一个css文件中引入另一个css文件
```
    @import "reset.css";    // 缺点： 效率低
```

- @charset
> 声明样式表的字符编码
```
    @charset "UTF-8";
```

- 用户样式
> 自己规定的浏览器样式
```
    chrome: default/user stylesheets/custom.css -- 文件位置

    // 修改的样式会应用到整个浏览器
```

- 样式层叠
    1. 元素内嵌样式 - 全局属性style定义的样式
    2. 文档内嵌样式 - 在style元素中定义的样式
    3. 外部样式 - 用link元素导入的样式
    4. 用户样式 - 用户定义的样式
    5. 浏览器样式 - 浏览器应用的默认样式
```
    // 改变样式层叠顺序
    color: red !important;
```

- 继承
> 与元素外观（文字颜色、字体等）相关的样式会被继承
> 与元素在页面上的布局相关的样式不会被继承
> 在样式中使用inherit可以强行实施继承，明确指示浏览器在该属性上使用父元素样式中的 值