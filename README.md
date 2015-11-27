### 1.[swiper](http://www.swiper.com.cn/)

#### 1.1.swiper 概述
* Swiper常用于移动端网站的内容触摸滑动
* Swiper是纯javascript打造的滑动特效插件，面向手机、平板电脑等移动终端。 
* Swiper能实现触屏焦点图、触屏Tab切换、触屏多图切换等常用效果。
*  Swiper开源、免费、稳定、使用简单、功能强大，是架构移动终端网站的重要选择！
### 2.swiper的使用
* 通过[官网](http://www.swiper.com.cn/)下载插件
* 加载插件，需要用到的文件有swiper.min.js和swiper.min.css文件
```
<!DOCTYPE html>
<html>
<head>
    ...
    <link rel="stylesheet" href="path/to/swiper.min.css">
</head>
<body>
    ...
    <script src="path/to/swiper.min.js"></script>
</body>
</html>
```
* 一般都会用到zepto.js或者是jQuery，也可以加载进来
* HTML写法,定义在`swiper-container`类中，这就是滑动的主容器所有的组件都要放在里边，
然后在里边定义`swiper-wrapper`类中，然后在`swiper-slide`中加如滑动的每一项
```
<div class="swiper-container">
    <div class="swiper-wrapper">
        <div class="swiper-slide">Slide 1</div>
        <div class="swiper-slide">Slide 2</div>
        <div class="swiper-slide">Slide 3</div>
    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>   
    <!-- 如果需要导航按钮 -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div> 
    <!-- 如果需要滚动条 -->
    <div class="swiper-scrollbar"></div>
</div>
导航等组件可以放在container之外
```
* 初始化swiper,要挨着body标签
```
<body>
  <script>        
  var mySwiper = new Swiper ('.swiper-container', {
    direction: 'vertical',
    loop: true,
    // 如果需要分页器
    pagination: '.swiper-pagination',  
    // 如果需要前进后退按钮 也可以自己写样式，只要改变下边的类名为自己定义的就可。
    //有时候会觉得那个箭头有点丑，所以就自己定义
    nextButton: '.swiper-button-next',
    prevButton: '.swiper-button-prev',  
    // 如果需要滚动条
    scrollbar: '.swiper-scrollbar',
  })        
  </script>
</body>
```
### 3.常用的[初始化](http://www.swiper.com.cn/api/basic/2014/1215/21.html)属性的定义，.1可以点击了解
#### 3.1.好玩的属性
* `paginationBulletRender(index, className)`可以制作tab奥
```
    var mySwiper = new Swiper('.swiper-container',{
        pagination: '.my-pagination',
        paginationClickable: true,
        paginationBulletRender: function (index, className) {
            switch (index) {
                case 0: name='Swiper应用';break;
                case 1: name='Swiper教程';break;
                case 2: name='Swiper介绍';break;
                default: name='';
            }
            return '<span class="' + className + '">' + name + '</span>';
        }
    })
```

