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
    width: 200px;
    height: 100px;
    background-color: #c1a3b8;
    &:nth-child(1) {
      clip-path: polygon(
        20px 0,
        180px 0,
        200px 20px,
        200px 80px,
        180px 100px,
        20px 100px,
        0px 80px,
        0 20px
      );
    }
    &:nth-child(2) {
      // x方向半径 y方向上半径 at 椭圆中心点的位置
      // border: 10px solid #e1cfd8;
      clip-path: ellipse(50% 50% at 50% 50%);
    }
  }
}
</style>