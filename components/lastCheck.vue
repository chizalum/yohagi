<template>
  <div>
    <div class="first-row">
      <div class="new-select">
        <p class="select-txt">Products</p>
      </div>
      <div class="sixth-div">
        <hr class="rule" />
        <div class="seventh-div">
          <div class="address-div">
            <p class="women-txt">Women Tops Solid Color</p>
            <p class="ex">X1</p>
          </div>
          <div class="radio-div">
            <p class="five-text"><span class="span">N</span>500</p>
          </div>
        </div>
      </div>

      <div class="sixth-div">
        <hr class="rule" />
        <div class="seventh-div">
          <div class="address-div">
            <p class="women-txt">Women Tops Solid Color</p>
            <p for="ex" class="ex">X1</p>
          </div>
          <div class="radio-div">
            <p class="five-text"><span class="span">N</span>500</p>
          </div>
        </div>
      </div>
    </div>
<div class="second-row">
    <div class="select-div">
      <p class="select-txt">Select your preferred delivery type</p>
    </div>
    <div class="sixth-div">
      <hr class="rule" />
      <div class="address-div">
        <p class="home-txt">Home Delivery</p>
        <label for="radio-input" class="five-txt"
          >5 semi crescent, oba-akran ave...</label
        >
        <p class="change-txt">change</p>
      </div>
    </div>
    </div>
    <div class="third-row">
    <div class="select-div">
      <p class="select-txt">Select your preferred delivery type</p>
    </div>
    <div class="sixth-div">
      <hr class="rule" />
      <div class="address-div">
        <p class="home-txt">Pay on Delivery</p>
        <label for="radio-in" class="five-txt">POS Only</label>
      </div>
    </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "lastCheck",
};
</script>
  
  <style scoped>
.full-screen {
  margin: 0 0 0 0;
  background: #ffffff;
  height: max-content;
}

.select-div {
  margin: 0 0 0 4%;
}

.new-select {
  margin: 0 0 0 4%;
  padding-top: 31px;
}

.select-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #7d8597;
  margin: 0 0 0 0;
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

.home-txt {
  margin: 16px 0 0 0;
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

.change-txt {
  margin: 4px 0 0 0;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 18px;
  text-decoration-line: underline;
  color: #0ddf7a;
}

.radio-div {
  margin: 0 8% 0 auto;
  justify-self: flex-end;
}

.five-text {
  margin: 0 0 0 0;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 21px;
  text-transform: uppercase;
  color: #2f2f2f;
}

.women-txt {
  margin: 0 0 0 0;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 100;
  font-size: 14px;
  line-height: 17px;
  color: #001845;
}

.ex {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 900;
  font-size: 14px;
  line-height: 17px;
  margin: 7px 0 0 0;
  color: #001845;
}

.span {
  text-decoration-line: line-through;
}

.first-row {
  background: #ffffff;
  padding-bottom: 25px;
}

.second-row {
  background: #ffffff;
  padding-bottom: 30px;
  padding-top: 30px;
  margin: 12px 0 0 0;
}

.third-row {
  background: #ffffff;
  padding-bottom: 209px;
  padding-top: 30px;
  margin: 12px 0 12px 0;
}
</style>