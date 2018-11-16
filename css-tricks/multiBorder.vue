<template>
  <main>
    <div class="round"></div>
    <div class="square"></div>
    <div class="radius"></div>
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

  .round {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    // x方向的偏移 y方向的偏移 模糊距离 阴影扩张半径 色值
    box-shadow: 0 0 0 10px #6b6575, 0 0 0 20px #99758d, 0 0 0 30px #af8da5,
      0 0 0 40px #c1a3b8, 0 0 0 50px #d8c2d0, 0 0 0 60px #e1cfd8;
  }
  .square {
    width: 100px;
    height: 100px;
    border: 4px solid #6b6575;
    background-color: #e1cfd8;
    outline: #6b6575 dotted 4px;
    outline-offset: -14px;
  }
  // FIXME: 计算一下box-shadow 和 outline width 关系
  .radius {
    width: 200px;
    height: 100px;
    box-shadow: 0 0 0 5px #af8da5;
    border-radius: 10px;
    outline: #af8da5 solid 5px;
  }
}
</style>