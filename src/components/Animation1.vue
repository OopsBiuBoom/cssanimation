<template>
    <div></div>
</template>

<style scoped lang="scss">
    /* 设置主体边框，并添加两个伪元素，一个位于左上角，边框设置左、上。一个位于右下角，边框设置右下。当鼠标放在主体时，使用渐变动画，把两个辅助的伪元素大小增大到比主体即可。*/
    
    // 定义边框颜色
    $boardColor: red;

    div {
        position: relative;
        width: 180px;
        height: 100px;
        border: 1px solid $boardColor;

        // 添加两个伪元素
        &::before, &::after {
            content: "";
            position: absolute;
            height: 20px;
            width: 20px;
            // 设置过渡效果
            transition: .3s ease-in-out;
        }

        // 设置伪元素的位置和边框
        &::before {
            top: -5px;
            left: -5px;
            border-left: 1px solid $boardColor;
            border-top: 1px solid $boardColor;
        }

        // 设置伪元素的位置和边框
        &::after {
            bottom: -5px;
            right: -5px;
            border-right: 1px solid $boardColor;
            border-bottom: 1px solid $boardColor;
        }

        // hover时调整大小
        &:hover::after {
            width: calc(100% + 9px);
            height: calc(100% + 9px);
        }

         &:hover::before {
            width: calc(100% + 9px);
            height: calc(100% + 9px);
        }
    }
</style>