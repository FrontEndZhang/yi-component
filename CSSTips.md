# CSS实用技巧

## 清除浮动

实质：其实就是在父元素最后一个子元素的最后面添加了一个看不见的块元素，然后把这个块元素加上clear : both

```
.clearfix {
	content : "";
	display : block;
	height : 0;
	visibility : hidden;
	clear : both
}
// 兼容ie6 - 7
.clearfix {
	*zoom: 1;
}
```

## CSS全局变量获取和修改

```css
body {
    // 设置全局变量
    --theme-color: #05BF83;
}
```

在css中获取使用

```
// css获取
color: var(--theme-color);
```

在JavaScript中修改（后期通过后端来修改css全局变量）

```
// JavaScript修改css全局变量
document.body.style.setProperty('--theme-color', '#ff0000');
```

## 图片后的文字垂直居中

原因：inline-block之后的基线会在底部，所以后面的文字也在底部

```
图片 {
  vertical-align: middle;
}

文字 {
  vertical-align: middle;
}
```

## 字体图标垂直水平居中

wrapper内的文字和img也要用span包裹起来,如果有图片，图片也要vertical-align: middle;才可以哦

``` html

<div class="wrapper">
    <!-- span > img -->
   <span class="iconfont">&#xe8cf;</span>
</div>

```

```css
.wrapper {
 height: 设定的高度;
 line-height: 设定的高度;
 text-align: center;
 
 span {
  display: inline-block;
  vertical-align: middle;
  font-size: 设定的大小;
 }
}
// 如果有图片
// img {
//       vertical-align: middle;
// }
```



# CSS小知识

## background-size：contain 和 cover 的区别

1、在 no-repeat 情况下，如果容器宽高比与图片宽高比不同，

cover:图片宽高比不变、铺满整个容器的宽高，而图片多出的部分则会被裁掉；cover 即为”塞满“

contain:图片自身的宽高比不变，缩放至整个图片自身能完全显示出来，所以容器会有留白区域。contain 即为“包含”，我图片虽然缩放了，但是整个图是被“包含”在里面了，完整显示，不能裁剪。

2、在 repeat 情况下：

cover 与上述相同；

contain：容器内至少有一张完整的图，容器留白区域则平铺背景图，铺不下的再裁掉。

