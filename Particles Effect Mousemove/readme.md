# Particles Effect Mousemove ▫▪

> [视频链接](https://www.youtube.com/watch?v=j87gaYoBmso) 📺
>
> [Particles.js official Website](https://vincentgarreau.com/particles.js/) ◾



## 实现效果

<img src="https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210804114142_particles_move.gif" alt="particles move" style="zoom:80%;" />



## 涉及语法

+ [mix-blend-mode: screen](https://developer.mozilla.org/zh-CN/docs/Web/CSS/mix-blend-mode) 混合模式

  > 描述了元素的内容应该与元素的直系父元素的内容和元素的背景如何混合。
  >
  > [CSS混合模式mix-blend-mode/background-blend-mode简介 —— 张鑫旭](https://www.zhangxinxu.com/wordpress/2015/05/css3-mix-blend-mode-background-blend-mode/) 



## JS外库引用

**[🎈particles.js](https://github.com/VincentGarreau/particles.js)** —— **A lightweight JavaScript library for creating particles**

1. 下载选中的js文件，导入到项目中

   <img src="https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210804115015.png" alt="image-20210804115015583" style="zoom:50%;" />

2. 在html中引入相应的js

   ```html
   <script src="particles.js"></script>
   <script src="app.js"></script>
   ```

3. 自定义配置app.js，修改参数

   比如粒子数量，样式，颜色等等