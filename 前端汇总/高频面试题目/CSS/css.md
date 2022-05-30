#### CSS可继承属性

```css
字体：font、font-family、font-size、font-style、font-variant、font-weight
字母间距：letter-spacing
可见性：visibility
文字展示：line-height、text-align、text-indent、text-transform
字间距：word-spacing
```

#### 清除浮动的方法以及优缺点

```css
1、为什么清除浮动?
当子元素开启浮动并且父元素没有设置高度的时候，父元素的高度不会被撑开，也就是会发生高度塌陷的问题，这时候就要清除浮动。
2、清除浮动的方法?
(1)父元素固定宽高；优点：简单、代码量少、没有兼容问题；缺点：内部元素高度不确定的情况下无法使用；
(2)添加新元素；优点：简单、代码量少、没有兼容问题；缺点：需要添加无语义的html元素，代码不够优雅，不方便维护；
在最后添加一个空的div标签，并且利用CSS样式清除浮动(clear:both)；
(3)使用伪元素；优点：仅用CSS实现，不容易出现怪问题；缺点：仅支持IE8以上和非IE浏览器；
(4)触发父元素BFC：优点：仅用CSS实现，代码少，浏览器支持好；缺点：使用overflow:hidden触发BFC的情况下，可能使内部本应该正常显示的元素被裁剪。
```

#### BFC（Block Formatting Context）块级格式化上下文

```css
浮动的特点：
(1)元素设置浮动之后，会从文档流中脱离，不再占用文档流的位置；
(2)设置浮动的元素不会超出它的父元素；
(3)设置浮动的元素不会覆盖其前面开启浮动的元素；
(4)如果浮动的元素上边是一个没有浮动的块元素，则浮动元素无法上移；
(5)浮动元素不会盖住文字，可以实现文字环绕图片的效果。
浮动的作用：
让一些样式可以水平排列。

BFC(Block Formatting Context):块级格式化上下文
	是CSS中一个隐含的属性，开启BFC该元素会变成一个独立的布局区域，里面的元素不会影响到外部的元素。
开启BFC的方式：
注意：display:table也可以生成BFC的原因在于Table会默认生成一个匿名的table-cell，是这个匿名的table-cell生成了BFC。
(1)根元素，即HTML标签；
(2)浮动元素：float值为left、right；
(3)overflow值不为 visible，为auto、scroll、hidden；
(4)display值为inline-block、table-cell、table-caption、table、inline-table、flex、inline-flex、grid、
inline-grid；
(5)定位元素：position值为absolute、fixed；
解决什么问题?
(1)外边距重叠；
(2)高度塌陷的问题；
```

