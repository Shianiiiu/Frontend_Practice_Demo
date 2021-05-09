# Text Hover Effect 01 🥔

> [油管链接📺](https://www.youtube.com/watch?v=sLhiZM_Njd0&list=WL&index=4)



## 实现效果

![text hover](https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210509155649_text_hover.gif)

## 重要语法

- `display: inline-flex`
- `line-height: 1em;`
- `letter-spacing: -1em;`



## 问题解决

```html
<span>d</span><span>o</span><span>nate</span>
```

单词'donate'使用`span`标签拼接，注意如果span之间在编辑器中有换行，则会有<u>换行间隙</u>。

(可以阅读下这篇博客：[inline-block布局产生间隙的原因及解决办法](https://blog.csdn.net/gladys_1111/article/details/77279985))

为了实现抽屉式悬停动画效果，保留字母`'O'`，借助`letter-spacing: -1em`:

```css
h2 span {
    display: inline-flex;
}

h2 span:nth-child(odd) {
	letter-spacing: -1em;
    overflow: hidden;
}

```

设置字母间隔为`-1em`后，`'d'` 和 `'nate'`重叠，此时的盒子宽度变成0：

![image-20210509162612461](https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210509162612.png)

设置`display: inline-flex;`使`span`标签变成“块级”（我猜的🤦‍♂️或者是BFC？），**目的是为了让`overflow: hidden;`生效。** 

至于`inline-flex`：将对象作为内联弹性伸缩盒显示，意思是根据元素内容决定伸缩盒的宽。[看看这篇文章](https://blog.csdn.net/jiang12138/article/details/100178726)

然后，因为`overflow: hidden`的作用，`'d'` 和 `'nate'`就被隐藏了。

![image-20210509163514982](https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210509163515.png)

通过hover伪类，悬停时将字母间距`letter-spacing: 0;`，实现“抽屉打开”效果。

---

还有两处文字，由`i`标签（呈现斜体），再设置伪元素`before`和`after` 。里头的定位absolute尤其要注意，仔细琢磨吧我似懂非懂，包括`text-align: center`是个谜。

```css
h2 i {
    position: absolute;
    font-size: 0.2em;
    color: #777;
    line-height: 1em;
    font-weight: 400;
    transform: translateX(-50%);
    -webkit-transform: translateX(-50%);
    -moz-transform: translateX(-50%);
    -ms-transform: translateX(-50%);
    -o-transform: translateX(-50%);
    /* margin: 10px 0; */
}

h2 i::before {
    position: absolute;
    width: 100%;
    content: 'Oxygen';
    text-align: center;
    transition: 0.5s ease-in-out;
    -webkit-transition: 0.5s ease-in-out;
    -moz-transition: 0.5s ease-in-out;
    -ms-transition: 0.5s ease-in-out;
    -o-transition: 0.5s ease-in-out;
    display: initial;
}

h2:hover i::before {
    opacity: 0;
    letter-spacing: 2em;
}

h2 i::after {
    content: 'Human & Nature';
    opacity: 0;
    visibility: hidden;
    transition: 0.5s ease-in-out;
    -webkit-transition: 0.5s ease-in-out;
    -moz-transition: 0.5s ease-in-out;
    -ms-transition: 0.5s ease-in-out;
    -o-transition: 0.5s ease-in-out;
}

h2:hover i::after {
    opacity: 1;
    visibility: visible;
}
```

