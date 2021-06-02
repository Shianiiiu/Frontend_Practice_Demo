# Button Ripple Hover Effect 波纹悬停动效 🌊

> 视频链接：[Button Ripple Hover Effects using CSS & Javascript](https://www.youtube.com/watch?v=WOSaNbpHNqU&t=5s) 📺



## 实现效果

<img src="https://picgo-bed-1305701422.cos.ap-shanghai.myqcloud.com/picgo/20210602110551.gif" alt="button ripple" style="zoom:80%;" />



## 总体思路

1. 蓝色”遮罩层“使用伪元素绝对定位
2. 在button上添加鼠标移动监听事件
3. 得到鼠标移动的点在button容器中的相对位置
4. 根据第3步的位置改变伪元素的left，top值
5. 鼠标悬停则改变蓝色”遮罩层“的宽高



## 代码示例

- CSS部分

  ```css
  .btn::before {
  	content: '';
      position: absolute;
      top: var(--y);
      left: var(--x);
      width: 0;
      height: 0;
      border-radius: 50%;
      background-color: #2196f3;
      transition: width 0.5s, height 0.5s;
      transform: translate(-50%, -50%);
  }
  
  .btn:hover::before {
      width: 300px;
      height: 300px;
  }
  ```

- JS部分
    ```js
    <script>
        const btn = document.querySelector('.btn')

        btn.onmousemove = function (e) {
            const x = e.pageX - btn.offsetLeft;
            const y = e.pageY - btn.offsetTop;
            btn.style.setProperty('--x', x + 'px');
            btn.style.setProperty('--y', y + 'px');
        }
    </script>
    ```

