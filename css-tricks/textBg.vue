<template>
  <main>
    <div>ずっと前から好きでした</div>
    <div>ずっと前から好きでした</div>
    <div>ずっと前から好きでした</div>
    <div>ずっと前から好きでした</div>
    <div>ずっと前から好きでした</div>
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
    position: relative;
    padding: 10px;
    cursor: pointer;
    user-select: none;
    &:nth-child(1) {
      &::before {
        content: "";
        position: absolute;
        left: 0;
        bottom: 0;
        width: 100%;
        height: 2px;
        background-color: #af8da5;
        transform: scaleX(0);
        // 在:hover离开时 以这个为原点 scaleX(1)->scale(0)
        transform-origin: 100% 0;
        transition: transform 1s ease;
      }
      &:hover::before {
        transform: scaleX(1);
        // 在:hover进入时 以这个为原点 scaleX(0)->scale(1)
        transform-origin: 0 0;
      }
    }
    &:nth-child(2) {
      background-color: #d8c2d0;
      overflow: hidden;
      &::before {
        content: "";
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        //设置径向渐变
        background: radial-gradient(circle, #99758d 10%, transparent 10.01%);
        transform: scale(10, 10);
        opacity: 0;
        transition: transform 0.3s, opacity 0.5s;
      }
      &:hover {
        background-color: #e1cfd8;
      }
      &:active::before {
        transform: scale(0, 0);
        opacity: 0.3;
        //设置初始状态
        transition: 0s;
      }
    }
    &:nth-child(3) {
      // background-color: ;
      background: linear-gradient(135deg, transparent 10px, #d8c2d0 11px) top
          left,
        linear-gradient(-45deg, transparent 10px, #d8c2d0 11px) bottom right;
      background-repeat: no-repeat;
      background-size: 50% 10%;
    }
    &:nth-child(4) {
      background: #e1cfd8;
      color: #99758d;
      animation: blink 1s infinite;
      animation-direction: alternate;
      text-shadow: 0 0 0 #fff;
    }
    @keyframes blink {
      to {
        color: transparent;
      }
    }
    &:nth-child(5) {
      background: #e1cfd8;
      &:hover {
        animation: shake 1s ease-in-out;
      }
    }
    @keyframes shake {
      from {
        transform: translateX(0);
      }
      10%,
      30%,
      50%,
      70%,
      90% {
        transform: translateX(-10px);
      }

      20%,
      40%,
      60%,
      80% {
        transform: translateX(10px);
      }
    }
  }
}
</style>