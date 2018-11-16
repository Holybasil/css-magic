<template>
  <main>
    <section :style="{backgroundClip: value}">ずっと前から好きでした</section>
    <label for="border" @click="changeBg('border')"><input type="radio" name="clip" id="border"><span>border-box</span></label>
    <label for="padding" @click="changeBg('padding')"><input type="radio" name="clip" id="padding" checked><span>padding-box</span></label>
    <label for="content" @click="changeBg('content')"><input type="radio" name="clip" id="content"><span>content-box</span></label>
  </main>
</template>

<script>
export default {
  data() {
    return {
      value: "padding-box"
    };
  },
  methods: {
    changeBg(value) {
      this.value = `${value}-box`;
    }
  }
};
</script>

<style lang="scss" scoped>
main {
  width: 100%;
  padding: 40px 80px;
  box-sizing: border-box;
  background-color: #6b6575;
  section {
    padding: 20px;
    background-color: #fff;
    border: 10px solid hsla(0, 0%, 100%, 0.5);
    // background-clip: ;
  }
  label {
    & + label {
      margin-left: 20px;
    }
    & > * {
      vertical-align: middle;
    }
    span {
      color: #fff;
    }
  }
}
</style>