# Starbucks Landing Page 「Responsive」

> 教程视频油管📺 [P1](https://www.youtube.com/watch?v=91Q6RvKvd7o)、[P2响应式](https://www.youtube.com/watch?v=HXKNedyDbNE)

## 页面展示

![image-20210421204039598](https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421204039.png)

 **[效果预览](https://shianiiiu.github.io/Frontend_Practice_Demo/Starbucks_Landing_Responsive/index.html)**

## 知识点巩固

#### 1、切换菜单按钮

`Node.classList.toggle('active')`添加或移除类名active，开关效果。

```js
function toggleMenu() {
            var menuToggle = document.querySelector('.toggle');
            var nav = document.querySelector('.nav');
            menuToggle.classList.toggle('active');
            nav.classList.toggle('active');
        }
```

<img src = "https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421205754.png" style="zoom:70%"  />

<img src = "https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421205848.png" style="zoom:70%"  />



#### 2、绘制绿色背景装饰图

<img src = "https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421210253.png" width = "200px" />

```html
<div class="circle"></div>
```

```css
.circle {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: #017143;
    clip-path: circle(600px at right 850px);
}
```

其中使用到`clip-path`属性：**用于指定使用一个基本图形或者内联或外部的SVG路径作为剪裁路径对元素进行裁剪。**

搭配使用`circle`函数：**`circle()`函数是一个图形函数，用于指定某种基本图形[basci-shape](http://www.htmleaf.com/ziliaoku/qianduanjiaocheng/basic-shape.html)类型。**

```css
circle() = circle( [<shape-radius>]? [at <position>]? )
/* where.. */
<shape-radius> = <length> | <percentage> | closest-side | farthest-side
```

设置`position`参数的语法和[background-position](http://www.htmleaf.com/ziliaoku/qianduanjiaocheng/background-position.html)相同。使用`position`是必须带有`at`关键字。

#### 3、快速改变图标颜色黑色至白色

![image-20210421211513185](https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421211513.png)		  ![](https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421211527.png) 

```css
filter: invert(1);
```

`filter`属性：**将模糊或颜色偏移等图形效果应用于元素**。滤镜通常用于**调整图像，背景和边框的渲染**。

`invert`函数反转输入图像。`amount` 的值定义转换的比例。`100%` 的价值是完全反转。值为 `0%` 则图像无变化。值在 `0%` 和 `100%` 之间，则是效果的线性乘数。 若值未设置值，默认为 `0`。

[MDN filter](https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter)

#### 4、导航栏悬停下划线抖动

![image-20210421212812026](https://gitee.com/shianiiiu/picgo_bed/raw/master/img/20210421212812.png)

```css
.nav li a {
    border-bottom: 3px solid transparent;
}
```

```css
.nav li a:hover{
    border-bottom: 3px solid #017143;
}
```

在悬停之前**先填充**下划线，保证粗细相等，设置颜色**透明transparent。**

