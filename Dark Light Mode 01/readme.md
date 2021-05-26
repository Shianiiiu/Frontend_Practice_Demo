# Dark & Light Mode User Card  明暗切换应用🌗

> [油管视频📺](https://www.youtube.com/watch?v=JhVMAzrvdos&t=271s)



## 实现效果

![dark mode](https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210506230844_darkmode01.gif)



## 问题解决

右上角的明暗切换图标使用`i标签`设置，和视频中使用伪元素在`content`中填写相应图标的`Unicode`不同

```html
<div class="toggle"><i class="fas fa-moon"></i></div>
```

JS实现切换功能：

```js
toggle.onclick = function() {
    sec.classList.toggle('dark');

    if(icon.classList.contains('fa-moon')) {
        icon.classList.replace('fa-moon','fa-sun')
    }else {
        icon.classList.replace('fa-sun','fa-moon')
    }
}
```

