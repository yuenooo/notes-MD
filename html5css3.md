---
sidebar: auto
---

# HTML5CSS3

# CSS



## 元素分类

- 非替换元素：
  - 大多数元素都是非替换元素

- 替换元素：

  - 并非由文档内容直接表示 eg: `img` 与 `input`

- 元素分类：

  - 块级元素和行内元素

## 样式加载方式

- `link`加载
- `style`标签
- `style`标签中` @import`引入   需要放在最前面  否则不起作用
- 内联样式

```html
  <-- link 引入  只能在 head 内引入-->
  <link rel="stylesheet" href="demo1.css" type="text/css" title="demo1">
  
  <-- 页面内 style 标签   -->
  <style type="text/css">
    .demo{
        font-size:14px;
      color:red;
    }
  </style>
  
   <-- style标签  @import 引入外链css  -->
    <style  type="text/css">
     @import url(./demo.css)
    .demo{
        font-size:14px;
      color:red;
    }
   </style>
   
   <-- 内联样式 直接写在样式上  -->
   <p stype="font-size:12px;color:red" >hahaha</p>
```

## 候选样式表

- **`rel` 设为 **`alternate` `stylesheet` 并且需要设置 `title` 属性
- 进行测试 只有ie浏览器支持（火狐没有测试成功）

```html
<-- 不带alternate 为默认属性 -->
<link rel="stylesheet" href="demo1.css" type="text/css" title="demo1">
<link rel="alternate stylesheet" href="demo2.css" type="text/css" title="demo2">

```

## 选择器

- 元素选择器 ` div` ` span` `p`
- 通配选择器  `*`
- 类选择器 ` .demo`
- ID选择器  `#demo`
- 多类选择器  ` .demo.demo1`
- 属性选择器  

  - `h1[class]`   `input[type]`

  - `h1[class='demo']`    `input[type='text']`
  - 部分属性选择器   `h1[class~='demo']`   `( <h1 class="demo flag"> demo </h1> )`
  - 匹配属性选择器   

    - 以`bar`开头的所有元素  `span[class^='bar']` 
    - 等于`bar`或者以`bar-`开头的所有元素  span[class|='bar']
    - 以`bar`结尾的所有元素  `span[class$='bar']`
    - 包含`bar`字符的所有元素  `span[class*='bar']`  
    - 可以用来筛选`img` 的`src` 以及 `input` 的 `type` 等各种元素

- 后代选择器   `div span`
- 子元素选择器 `div>span`
- 相邻元素选择器 `div +span`
- 伪类选择器 

  - 一般伪类 `a:hover`
  - 前：`p:before`
  - 后：`p:after`

- 其他选择器

  - 选择第一个子元素   `p:first-child`
  - 首字母选择器  `p:first-letter`
  - 首行选择器 `p:first-line`

## 结构和层叠

- 各种选择器权重：
  - ID选择器：0，1，0，0
  - 类选择器，属性选择和伪类选择器：0，0，1，0
  - 元素选择器和伪元素：0，0，0，1
  - 内联样式：1，0，0，0
  - `!important`

## 继承

- 样式继承：
  - 不能继承的样式属性：边框 外边距 内边距 背景

## Web安全颜色

- 指在256色计算机系统上总能避免抖动的颜色。
  - RGB值 20%和51的倍数
  - 十六进制：00 33 66 99 CC FF  例如：#9CF

## 长度单位

- 绝对长度单位：
  - in：英寸
  - cm：厘米
  - mm：毫米
  - pt：点 一英寸=72点
  - pc：派卡 一派卡=12点

- 相对长度单位：
  - px：像素
  - em：1em等于 font-size的值
  - ex:  所用字体中小写x的高度

## 关键字

- `none`
- `inherit`： 使一个属性的值与其父元素的值相同

## 文本属性

- 首行缩进：`text-indent`

- 文本属性连写：`font`
  - `font:font-style font-weight font-size/line-height font-family   `
  - eg：`font: italic 600 16px/40px 微软雅黑;  `
  - 注意：文字大小和字体为必选项

- 字体变形：`font-variant`
  - `normal`
  - `small-caps` 小型大写字母