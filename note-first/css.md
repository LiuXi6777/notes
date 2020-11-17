[^_^]:[TOC]**
[1.css绘三角形](#1css绘三角形)
## 1.css绘三角形
```
采用的是相邻边框连接处的均分原理。将元素的宽高设为0，只设置border，把任意三条边隐藏掉（颜色设为 transparent），剩下的就是一个三角形。
```
```
 #demo {
  width: 0;
  height: 0;
  border-width: 20px;
  border-style: solid;
  border-color: transparent transparent red transparent;
}
```
## 2.css新特性

- 新增各种CSS选择器	（:not(.input)：所有class不是“input”的节点）
- 圆角		（border-radius:8px）
- 多列布局	（multi-column layout）
- 阴影和反射	（Shadow\Reflect）
- 文字特效		（text-shadow）
- 文字渲染		（Text-decoration）
- 线性渐变		（gradient）
- 旋转			（transform）
- 缩放，定位，倾斜，动画，多背景
例如：`transform:\scale(0.85,0.90)\translate(0px,-30px)\skew(-9deg,0deg)\Animation:`

## 3.flex:1
```
简介：CSS属性 flex 规定了弹性元素如何伸长或缩短以适应flex容器中的可用空间。这是一个简写属性，用来设置 flex-grow, flex-shrink 与 flex-basis。
```
**flex-grow**:CSS flex-grow 属性定义弹性盒子项（flex item）的拉伸因子。  
**flex-shrink**:CSS flex-shrink 属性指定了 flex 元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 flex-shrink 的值。  
**flex-basis**:CSS 属性 flex-basis 指定了 flex 元素在主轴方向上的初始大小。如果不使用 box-sizing 改变盒模型的话，那么这个属性就决定了 flex 元素的内容盒（content-box）的尺寸。
<‘width’>
width 值可以是 ; 该值也可以是一个相对于其父弹性盒容器主轴尺寸的百分数 。负值是不被允许的。默认为 auto。
content
基于 flex 的元素的内容自动调整大小。

*详情参看：*[flex:1详解](https://blog.csdn.net/qq_40138556/article/details/103967529)


