<template>
  <main>
    <div></div>
    <div></div>
    <div></div>
    <div><span>好きだよ</span></div>
    <div><span>好きだよ</span></div>
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
    background-color: #c1a3b8;
    &:nth-child(1) {
      width: 200px;
      height: 100px;
      // https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-radius
      border-radius: 50%/100% 100% 0 0;
    }
    &:nth-child(2) {
      width: 100px;
      height: 100px;
      border-radius: 100% 0 0 0;
    }
    &:nth-child(3) {
      width: 200px;
      height: 100px;
      border-radius: 50%/100% 0;
    }
    &:nth-child(4) {
      width: 200px;
      height: 100px;
      transform: skewX(-30deg);
      span {
        display: inline-block;
        // 基于tansform 的变形对display: inline 元素不起作用
        transform: skewX(30deg);
      }
    }
    &:nth-child(5) {
      width: 100px;
      height: 100px;
      transform: rotate(45deg);
      span {
        display: inline-block;
        transform: rotate(-45deg);
      }
    }
  }
}
</style>