<template>
  <main>
    <div></div>
    <div></div>
  </main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
main {
  width: 100%;
  height: 400px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  div {
    width: 150px;
    height: 150px;
    background: #99758d linear-gradient(to right, transparent 50%, #d8c2d0 0);
    border-radius: 50%;
    &:nth-child(1) {
      &::before {
        content: "";
        display: block;
        height: 100%;
        // 形成右半圆
        margin-left: 50%;
        border-radius: 0 100% 100% 0 / 0 50% 50% 0;
        background-color: #99758d;
        // 确定旋转中心 default [50% 50%]
        transform-origin: 0 50%;
        // turn 取值[0, 1]
        transform: rotate(0.1turn);
      }
    }
    &:nth-child(2) {
      &::before {
        // border: 1px solid #6b6575;
        content: "";
        display: block;
        margin-left: 50%;
        height: 100%;
        border-radius: 0 100% 100% 0 / 0 50% 50% 0;
        background-color: #99758d;
        transform-origin: 0 50%;
        // fill-mode forwards 表示动画完成之后保持最后的属性值
        // 相应的 backwards 表示在delay的时候就开始应用from 0 的属性值
        // TODO: animation 的各个属性
        animation: bg 3s step-end 1 forwards, spin 3s linear 2 forwards;
      }
      @keyframes spin {
        to {
          transform: rotate(0.5turn);
        }
      }
      @keyframes bg {
        to {
          background: #d8c2d0;
        }
      }
    }
  }
}
</style>