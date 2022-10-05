<template>
  <div class="modal-backdrop">
    <div class="modal-container">
      <p class="change-txt">Change Market</p>
      <p class="amet-txt">Amet minim mollit non deserunt ullamco est sit</p>
      <p class="market-txt">Markets</p>
      <select name="cars" class="selecter">
        <option value="volvo" class="place">Rayfield</option>
        <option value="saab" class="place">Lekki</option>
        <option value="opel" class="place">Oshodi</option>
        <option value="audi" class="place">Maryland</option>
      </select>
      <button class="btn" @click="$emit('closeModal')">
        <span>CHANGE</span>
      </button>
      <p class="cancel-txt" @click="$emit('closeModal')">Cancel</p>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "homeModal",

  data() {
    return {
      img: "modalimage.png",
    };
  },

  methods: {},
};
</script>
  
  <style scoped>
.modal-backdrop {
  height: 100vh;
  width: 100vw;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-container {
  position: fixed;
  margin: auto auto auto auto;
  width: 343px;
  height: 386px;
  background: #fffefa;
}

.assign-btn {
  width: 364px;
  height: 48px;
  background: #ffd60a;
  border-radius: 8px;
  border: none;
  margin: 24px auto 0 auto;
}

.assign-text {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #000000;
}

.change-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 21px;
  text-align: center;
  margin: 27px auto 0 auto;
  color: #000000;
}

.amet-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  color: #7d8597;
  margin: 10px auto 0 auto;
}

.market-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #001845;
  margin: 29px 0 0 18px;
}

.selecter {
  width: 308px;
  height: 57px;
  margin: 12px auto 0 auto;
  border: 1px solid #223263;
  border-radius: 3px;
  display: block;
  padding: 0 26px 0 26px;
}

.btn {
  width: 308px;
  height: 50px;
  margin: 66px auto 0 auto;
  background: #06d6a0;
  border-radius: 3px;
  border: none;
  display: block;
  cursor: pointer;
}

.change-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  text-transform: uppercase;
  color: #001845;
}

.cancel-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  margin: 27px auto 0 auto;
  color: #7d8597;
  cursor: pointer;
}
</style>