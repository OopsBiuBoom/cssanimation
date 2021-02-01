<template>
    <div></div>
</template>

<style scoped lang="scss">

    // 定义边框颜色
    $boardColor: red;
    
    div {
        position: relative;
        top: 100px;
        left: 100px;
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

        &::before {
            top: -5px;
            left: -5px;
            border-left: 1px solid $boardColor;
            border-top: 1px solid $boardColor;
        }

        &::after {
            bottom: -5px;
            right: -5px;
            border-right: 1px solid $boardColor;
            border-bottom: 1px solid $boardColor;
        }

        // hover时的处理
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