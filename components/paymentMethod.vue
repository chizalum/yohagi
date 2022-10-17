<template>
  <div class="full-screen">
    <div class="fifth-div">
      <p class="select-txt">Select your preferred Payment method</p>
    </div>
    <div class="sixth-div">
      <hr class="rule" />
      <div class="seventh-div">
        <div class="address-div">
          <label for="radio-input" class="home-txt"
            >Use Debit/Credit Card</label
          >
          <div class="img-div">
            <img src="visa.png" class="visa" />
            <img src="mastercard.png" class="mastercard" />
            <img src="verve.png" class="verve" />
          </div>
        </div>
        <div class="radio-div">
          <input
            type="radio"
            class="radio-input"
            name="home"
            value="semi-crescent"
          />
        </div>
      </div>
    </div>
    <div class="sixth-div">
      <hr class="rule" />
      <div class="seventh-div">
        <div class="address-div">
          <p class="home-txt">Pay on Delivery</p>
          <label for="radio-in" class="five-txt">POS Only</label>
        </div>
        <div class="radio-div">
          <input type="radio" class="radio-in" name="home" value="pickup" />
        </div>
      </div>
    </div>
    <div class="voucher-div">
      <p class="vouch-txt">Use Voucher</p>
      <hr class="new-rule" />
      <div class="code-div">
        <input type="text" placeholder="Voucher Code" class="insert" />
        <button class="sub-btn">
          <p class="app-txt">Apply</p>
        </button>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "paymentMethod",
};
</script>
  
  <style scoped>
.full-screen {
  margin: 0 0 0 0;
  background: #ffffff;
  height: max-content;
}

.fifth-div {
  margin: 0 0 0 0;
  padding-top: 19px;
  width: 100%;
}

.select-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #7d8597;
  margin: 0 0 0 4%;
}

.sixth-div {
  width: 100%;
  margin: 0 0 0 0;
}

.rule {
  opacity: 0.3;
  border: 1px solid #d7d7d7;
  margin: 20px auto 0 auto;
  width: 92%;
}

.seventh-div {
  margin: 18px 0 0 0;
  display: flex;
  flex-direction: row;
  width: 100%;
}

.address-div {
  margin: 0 0 0 9.3%;
  display: flex;
  flex-direction: column;
}

.img-div {
  margin: 8px 0 0 0;
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: center;
}

.visa {
  width: 46px;
  height: 46px;
  margin: 0 14px 0 0;
}

.mastercard {
  width: 60px;
  height: 45px;
  margin: auto 14px auto 0;
}

.verve {
  width: 68px;
  height: 27px;
  margin: auto 0 auto 0;
}

.home-txt {
  margin: 0 0 0 0;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
}

.five-txt {
  margin: 7px 0 0 0;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #7d8597;
}

.radio-div {
  margin: 16px 8% 35px auto;
  justify-self: flex-end;
}

.radio-input {
  margin: 0 0 0 0;
}

.radio-in {
  margin: 0 0 0 0;
}

input[type="radio"].radio-input {
  accent-color: #06d6a0;
  width: 16px;
  height: 16px;
  box-shadow: 0 0 0 1px var(#06d6a0);
  border: 2px solid #06d6a0;
}

input[type="radio"].radio-in {
  accent-color: #06d6a0;
  width: 16px;
  height: 16px;
  box-shadow: 0 0 0 1px var(#06d6a0);
  border: 2px solid #06d6a0;
}

input[type="radio"]:checked:after {
  border: 2px solid #06d6a0;
  box-shadow: 0 0 0 1px var(#06d6a0);
  background-color: var(#06d6a0);
  border-width: 0.2rem;
  outline: 2px solid #06d6a0;
}

.voucher-div {
  width: 100%;
  margin: 0 0 0 0;
  background: #f4f6fa;
  padding-top: 27px;
}

.vouch-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  margin: 0 0 0 4%;
  color: #000000;
}

.new-rule {
  border: 1px solid #dddddd;
  margin: 12px auto 0 auto;
  width: 92%;
}

.code-div {
  margin: 16px 0 0 0;
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 100%;
}

.insert {
  width: 56%;
  padding-left: 28px;
  height: 48px;
  border: 1px solid #a8a8a8;
  margin: 0 0 0 0;
}

.sub-btn {
  width: 30%;
  height: 52px;
  margin: 0 0 0 0;
  background: #216ed7;
  border-radius: 0px 2px 2px 0px;
  border: none;
}

.app-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  margin: 0 0 0 0;
  text-align: center;
  text-transform: uppercase;
  color: #ffffff;
}
</style>