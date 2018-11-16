<template>
  <main>
    <div class="airbnb"></div>
    <div class="progress">
      <div class="inner"></div>
    </div>
    <div class="card"></div>
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
  .airbnb {
    width: 200px;
    height: 200px;
    padding: 20px;
    // 原图片尺寸 120x38 以/分割的是bg-size
    background: #6b6575 url("./imgs/airbnb.png") no-repeat bottom right / 100px;
    background-origin: content-box; // 规定背景图片的定位是从哪里开始的
    // background-clip: content-box; // 规定背景渲染范围 是否涉及padding区域 是否涉及border
  }
  .progress {
    width: 300px;
    height: 12px;
    background-color: #e1cfd8;
    border-radius: 6px;
    .inner {
      width: 60%;
      height: 100%;
      border-radius: 6px;
      // TODO:
      background: repeating-linear-gradient(
        -45deg,
        #c1a3b8 25%,
        #99758d 0,
        #99758d 50%,
        #c1a3b8 0,
        #c1a3b8 75%,
        #99758d 0
      );
      background-size: 14px 14px;
      animation: panoramic 10s linear infinite;
    }
    @keyframes panoramic {
      to {
        background-position: 200% 0;
      }
    }
  }
  .card {
    width: 200px;
    height: 100px;
    background-image: radial-gradient(
      ellipse farthest-corner at 100px -10px,
      transparent 20px,
      #c1a3b8 21px
    );
  }
}
</style>