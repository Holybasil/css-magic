<template>
  <main>
    <div class="ferrisWheel">
      <div class="wheel">
        <svg height="250" width="250" class="axis">
          <line x1="125" y1="0" x2="125" y2="250" style="stroke:#af8da5;stroke-width:2" />
          <line x1="16.75" y1="62.5" x2="233.25" y2="187.5" style="stroke:#af8da5;stroke-width:2" />
          <line x1="16.75" y1="187.5" x2="233.25" y2="62.5" style="stroke:#af8da5;stroke-width:2" />
        </svg>
        <div class="avatar">
          <img src="./imgs/双马尾.jpg" alt="">
        </div>
        <div class="avatar">
          <img src="./imgs/小女孩.jpg" alt="">
        </div>
        <div class="avatar">
          <img src="./imgs/帽子.jpg" alt="">
        </div>
        <div class="avatar">
          <img src="./imgs/眼睛.jpeg" alt="">
        </div>
        <div class="avatar">
          <img src="./imgs/短发.jpg" alt="">
        </div>
        <div class="avatar">
          <img src="./imgs/长发.jpg" alt="">
        </div>
      </div>
      <div class="bottomColumn"></div>
      <div class="bottomPanel"></div>
    </div>
    
  </main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
main {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: space-around;
  align-items: center;
  .ferrisWheel {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    .wheel {
      position: relative;
      width: 250px;
      height: 250px;
      border-radius: 50%;
      border: 2px solid #af8da5;
      .axis {
        animation: circular 9s infinite linear;
      }
      .avatar {
        position: absolute;
        top: 125px;
        left: 95px;
        width: 60px;
        height: 60px;
        border-radius: 50%;
        overflow: hidden;

        animation: circular-smooth-spin 9s infinite linear;
        &:nth-child(2) {
          animation-delay: -1.5s;
        }
        &:nth-child(3) {
          animation-delay: -3s;
        }
        &:nth-child(4) {
          animation-delay: -4.5s;
        }
        &:nth-child(5) {
          animation-delay: -6s;
        }
        &:nth-child(6) {
          animation-delay: -7.5s;
        }
        // 规定动画现在是运行时还是暂停时
        // animation-play-state: paused;
        img {
          width: 100%;
          height: 100%;
        }
      }
    }
    .bottomColumn {
      width: 60px;
      height: 60px;
      background-image: radial-gradient(
        circle at 50% -120px,
        transparent 125px,
        #af8da6 126px
      );
    }
    .bottomPanel {
      width: 125px;
      height: 2px;
      background-color: #af8da5;
    }
  }
}
@keyframes circular-smooth-spin {
  from {
    transform: rotate(0turn) translateY(125px) rotate(1turn);
  }
  to {
    // opacity: 1;
    transform: rotate(1turn) translateY(125px) rotate(0turn);
  }
}
@keyframes circular {
  from {
    transform: rotate(0turn);
  }
  to {
    transform: rotate(1turn);
  }
}
</style>