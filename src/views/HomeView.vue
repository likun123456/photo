<template>
  <div class="home">
    <div class="container">
        <div class="box">
            <div class="out-div out-front">
                <img src="../assets/1.jpg" alt="">
            </div>
            <div class="out-div out-back">
                <img src="../assets/2.jpg" alt="">
            </div>
            <div class="out-div out-left">
                <img src="../assets/3.jpg" alt="">
            </div>
            <div class="out-div out-right">
                <img src="../assets/4.jpg" alt="">
            </div>
            <div class="out-div out-top">
                <img src="../assets/5.jpg" alt="">
            </div>
            <div class="out-div out-bottom">
                <img src="../assets/6.jpg" alt="">
            </div>

            <div class="in-div in-front">
                <img src="../assets/3.jpg" alt="">
            </div>
            <div class="in-div in-back">
                <img src="../assets/4.jpg" alt="">
            </div>
            <div class="in-div in-left">
                <img src="../assets/5.jpg" alt="">
            </div>
            <div class="in-div in-right">
                <img src="../assets/6.jpg" alt="">
            </div>
            <div class="in-div in-top">
                <img src="../assets/7.jpg" alt="">
            </div>
            <div class="in-div in-bottom">
                <img src="../assets/8.jpg" alt="">
            </div>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HomeView',
};
</script>
<style>
*{
    /*初始化*/
    margin: 0;
    padding: 0;
}
body{
    /*100%窗口高度*/
    height: 100vh;
    /*弹性布局 居中*/
    display: flex;
    justify-content: center;
    align-items: center;
    /*径向渐变背景*/
    background: radial-gradient(circle at center,#333,#000);
}
/*最外层样式*/
.container{
    width: 500px;
    height: 500px;
    border: 1px solid;
    display: flex;
    justify-content: center;
    align-items: center;
}
/*外层div图片样式*/
.out-div img{
    width: 200px;
    height: 200px;
    /*对图片进行剪切 保留原始比例*/
    object-fit: cover;
}
/*内层div图片样式*/
.in-div img{
    width: 100px;
    height: 100px;
    /*对图片进行剪切 保留原始比例*/
    object-fit: cover;
}
/*盒子*/
.box{
    position: absolute;
    width: 200px;
    height: 200px;
    /*开启3D效果*/
    transform-style: preserve-3d;
    /*执行动画：动画名 时长 线性的 无限次播放*/
    animation: rotateAnimate 10s linear infinite;
}
/*外层div 统一的样式*/
.out-div{
    width: 200px;
    height: 200px;
    position: absolute;
    /*动画过渡*/
    transition: transform 1s ease-in;
}
/*外层div样式*/
.out-front{
    transform: translateZ(100px);
}
.out-back{
    transform: translateZ(-100px) rotateY(180deg);
}
.out-left{
    transform: translateX(-100px) rotateY(-90deg);
}
.out-right{
    transform: translateX(100px) rotateY(90deg);
}
.out-top{
    transform: translateY(-100px) rotateX(90deg);
}
.out-bottom{
    transform: translateY(100px) rotateX(-90deg);
}
/*鼠标移入，外层div各个面的样式变化*/
.container:hover .out-front{
    transform: translateZ(200px);
}
.container:hover .out-back{
    transform: translateZ(-200px) rotateY(180deg);
}
.container:hover .out-left{
    transform: translateX(-200px) rotateY(-90deg);
}
.container:hover .out-right{
    transform: translateX(200px) rotateY(90deg);
}
.container:hover .out-top{
    transform: translateY(-200px) rotateX(90deg);
}
.container:hover .out-bottom{
    transform: translateY(200px) rotateX(-90deg);
}
/*内层div 统一的样式*/
.in-div{
    margin-left: 50px;
    margin-top: 50px;
    width: 100px;
    height: 100px;
    position: absolute;
}
.in-front{
    transform: translateZ(50px);
}
.in-back{
    transform: translateZ(-50px) rotateY(180deg);
}
.in-left{
    transform: translateX(-50px) rotateY(-90deg);
}
.in-right{
    transform: translateX(50px) rotateY(90deg);
}
.in-top{
    transform: translateY(-50px) rotateX(90deg);
}
.in-bottom{
    transform: translateY(50px) rotateX(-90deg);
}

/*定义动画*/
@keyframes rotateAnimate {
    0%{
        transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
    }
    100%{
        transform: rotateX(360deg) rotateY(360deg) rotateZ(360deg);
    }
}

</style>
