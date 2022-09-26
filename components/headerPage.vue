<template>
  <div class="allscreen">
    <div class="status-bar">
      <div class="time-container">
        <p class="time">9:41</p>
      </div>
      <div class="network-container">
        <img
          src="mobile-signal.svg"
          alt="mobile-signal"
          class="mobile-signal"
        />
        <img src="wifi.svg" alt="wifi" class="wifi" />
        <img src="battery.svg" alt="battery" class="battery" />
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "headerPage",
};
</script>
  
  <style scoped>
.allscreen {
  height: auto;
  width: auto;
  white-space: nowrap;
}

.status-bar {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 0 0 0 0;
  width: 100%;
  max-width: 540px;
  background: transparent;
  height: auto;
  padding: 0;
  position: fixed;
  top: 0;
  left: auto;
  right: auto;
  background: #ffffff;
  z-index: 1000;
}

.time {
  margin: 14px 0 0 21px;
  font-family: "SF Pro Text";
  font-size: 15px;
  line-height: 18px;
  letter-spacing: -0.02em;
  color: #000000;
}

.battery {
  margin: 14px 19px 0 0;
}
</style>