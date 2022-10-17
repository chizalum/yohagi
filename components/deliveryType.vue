<template>
  <div>
    <div class="fifth-div">
      <div class="select-div">
        <p class="select-txt">Select your preferred delivery type</p>
      </div>
      <button class="add-btn">+ Add New Address</button>
    </div>
    <div class="sixth-div">
      <hr class="rule" />
      <div class="seventh-div">
        <div class="home-div"><img src="home.svg" class="home-img" /></div>
        <div class="address-div">
          <p class="home-txt">Home Delivery</p>
          <label for="radio-input" class="five-txt"
            >5 semi crescent, oba-akran ave...</label
          >
          <p class="change-txt">change</p>
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
        <div class="home-div"><img src="house.svg" class="home-img" /></div>
        <div class="address-div">
          <p class="home-txt">Pick Up</p>
          <label for="radio-in" class="five-txt"
            >Only from selected outlets</label
          >
        </div>
        <div class="radio-div">
          <input type="radio" class="radio-in" name="home" value="pickup" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "deliveryType",
};
</script>

<style>
.fifth-div {
  margin: 0 0 0 0;
  padding-top: 19px;
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-between;
}

.select-div {
  margin: 0 0 0 4%;
  width: 44%;
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

.add-btn {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 18px;
  margin: 0 4% 0 0;
  text-decoration-line: underline;
  color: #0ddf7a;
  background: none;
  border: none;
  cursor: pointer;
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

.home-div {
  width: 40px;
  height: 40px;
  margin: 7px 0 0 8%;
  background: #adadeb;
  border-radius: 50%;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.home-img {
  height: 18px;
  width: 18px;
  z-index: 1000;
  margin: 0 0 0 0;
}

.address-div {
  margin: 0 0 0 9.3%;
  display: flex;
  flex-direction: column;
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
</style>