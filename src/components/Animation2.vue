<template>
    <div class="colorbox"></div>
</template>

<style lang="scss" scoped>

    /* 定义一个底层，一个伪元素作为颜色层，一个遮罩层。颜色层不停的旋转即可 */ 

    // 旋转动画
    @keyframes rotate {
        100% {
		    transform: rotate(1turn);
	    }
    }

    // 圆角值
    $borderRadiue: 5px;

    .colorbox {
        // 需要设置position
        position: relative;
        // 剪裁超出的部分才有效果
        overflow: hidden;
        height: 100px;
        width: 180px;
        border-radius: $borderRadiue;
        z-index: 0;

        // 做旋转的伪元素
        &::before {
            content: '';
            position: absolute;
            z-index: -2;
            left: -50%;
            top: -50%;
            height: 200%;
            width: 200%;
            // 不重复使用图片来填充
            background-repeat: no-repeat;
            // 设置每个区域的所占的大小
            background-size: 50% 50%, 50% 50%;
            // 设置图片摆放的位置
            background-position: 0 0, 100% 0, 100% 100%, 0 100%;
            // 使用图片。linear-gradient()方法会生成一个渐变的图片
            background-image: linear-gradient(#399953, #399953), linear-gradient(#fbb300, #fbb300), linear-gradient(#d53e33, #d53e33), linear-gradient(#377af5, #377af5);
            // 使用动画
            animation: rotate 4s linear infinite;
        }

        // 边框宽度
        $borderWidth: 4px;
        // 设置一个伪元素为遮罩层
        &::after {
            content: '';
            position: absolute;
            background-color: white;
            z-index: -1;
            // 相当于边框
            left: $borderWidth;
            top: $borderWidth;
            border-radius: $borderRadiue;
            // 下面8px怎么处理成变量？类似`calc(100% - $borderWidth * 2px)`
            width: calc(100% - 8px);
            height: calc(100% - 8px);
        }
    }

</style>