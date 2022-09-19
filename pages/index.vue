<template>
  <div class="full-screen">
    <img src="yohagi.png" class="yohagi" alt="yohagi-symbol" />
    <spinner class="loader" />
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  layout: "login",
  created() {
    setTimeout(() => this.$router.push({ path: "/home" }), 4000);
  },
};
</script>

<style scoped>
.full-screen {
  background: url("~assets/white-background.png");
  width: 100%;
  max-width: 540px;
  min-height: 700px;
  height: 100vh;
  margin: 0 auto 0 auto;
}

.yohagi {
  margin: auto auto auto auto;
  position: absolute;
  display: block;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.loader {
  margin: auto auto auto auto;
  position: absolute;
  display: block;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
