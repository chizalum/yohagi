<template>
  <div class="full-screen">
    <div class="max-div">
      <div class="first-div">
        <div class="second-div">
          <img src="bluearrow.svg" class="arrow" @click="toShopping" />
          <p class="apple-txt">Check Out</p>
        </div>
        <img src="share.svg" class="share" />
      </div>
      <div class="flex-div">
        <div class="third-div">
          <div class="first-col">
            <div class="one-txt">1</div>
          </div>
          <hr class="horizontal-rule" />
          <div class="second-col">
            <div class="two-txt">2</div>
          </div>
          <hr class="horizontal-rule" />
          <div class="third-col">
            <div class="three-txt">3</div>
          </div>
        </div>
        <div class="fourth-div">
          <div class="first-col">
            <p class="delivery-txt">Delivery</p>
          </div>
          <div class="second-col">
            <p class="payment-txt">Payment</p>
          </div>
          <div class="third-col">
            <p class="summary-txt">Summary</p>
          </div>
        </div>
      </div>
      <div class="fifth-div">
        <div class="select-div">
          <p class="select-txt">Select your preferred delivery type</p>
        </div>
        <button class="add-btn">+ Add New Address</button>
      </div>
      <div class="sixth-div">
        <hr class="rule" />
        <div class="seventh-div">
            <img class="">
        </div>
      </div>
    </div>
  </div>
</template>

<!--fourt div thats a row as well for them delivery text-->

<script>
export default {
  name: "checkout",

  methods:{
    toShopping(){
    this.$router.push("/shoppingcart");
   },
}
};

</script>

<style>
.full-screen {
  width: 100%;
  height: 100%;
  margin: 0 0 0 0;
}

.max-div {
  max-width: 540px;
  margin: 0 auto 0 auto;
}

.first-div {
  display: flex;
  flex-direction: row;
  width: 100%;
  margin: 26px 0 0 0;
  justify-content: space-between;
  align-items: center;
  background: #ffffff;
}

.second-div {
  display: flex;
  flex-direction: row;
  align-items: center;
  width: auto;
  margin: 0 0 0 4%;
}

.arrow {
  width: 13.33px;
  height: 13.33px;
  margin: 0 0 0 0;
}

.apple-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  margin: 0 0 0 28px;
  color: #001845;
}

.share {
  width: 24px;
  height: 24px;
  margin: 0 4% 0 0;
}

.flex-div {
  display: flex;
  flex-direction: column;
  background: #f4f6fa;
  margin: 0 0 0 0;
  padding: 25px 4% 12px 4%;
}

.third-div {
  width: 82%;
  display: flex;
  flex-direction: row;
  margin: 0 auto 0 auto;
  justify-content: flex-start;
  align-items: flex-start;
}

.fourth-div {
  width: 92%;
  display: flex;
  flex-direction: row;
  margin: 0 auto 0 auto;
  justify-content: space-between;
  align-items: flex-start;
}

.first-col {
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
  align-items: flex-end;
}

.second-col {
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
}

.third-col {
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
}

.one-txt {
  width: 26px;
  height: 26px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: #ffffff;
  margin: 0 0 0 0;
  border-radius: 50%;
  text-align: center;
  background: #0ddf7a;
}

.two-txt {
  width: 26px;
  height: 26px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: #ffffff;
  margin: 0 0 0 0;
  border-radius: 50%;
  text-align: center;
  background: #0ddf7a;
}

.three-txt {
  width: 26px;
  height: 26px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: #ffffff;
  margin: 0 0 0 0;
  border-radius: 50%;
  text-align: center;
  background: #0ddf7a;
}

.horizontal-rule {
  opacity: 0.1;
  border: 1px solid #000000;
  width: 100%;
  height: 0;
  margin: 13px 0 0 0;
}

.delivery-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 12px 0 0 0;
}

.payment-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 12px 0 0 0;
}

.summary-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 12px 0 0 0;
}

.fifth-div {
  margin: 19px 0 0 0;
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
  justify-content: space-between;
}
</style>