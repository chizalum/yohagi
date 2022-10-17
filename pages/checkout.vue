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
          <hr class="horizontal-rule" :class="{ activeRule: live }" />
          <div class="second-col">
            <div class="two-txt" :class="{ activeOne: live }">2</div>
          </div>
          <hr class="horizontal-rule" :class="{ activeRuler: see }" />
          <div class="third-col">
            <div class="three-txt" :class="{ activeTwo: see }">3</div>
          </div>
        </div>
        <div class="fourth-div">
          <div class="first-col">
            <p class="delivery-txt">Delivery</p>
          </div>
          <div class="second-col">
            <p class="payment-txt" :class="{ paytext: live }">Payment</p>
          </div>
          <div class="third-col">
            <p class="summary-txt" :class="{ sumtext: see }">Summary</p>
          </div>
        </div>
      </div>
      <deliveryType v-if="show"></deliveryType>
      <PaymentMethod v-if="view"></PaymentMethod>
      <lastCheck v-if="see"></lastCheck>
      <div class="btn-outline">
        <div class="bttn-div">
          <p class="vat-txt">Shipping:</p>
          <p class="naira-txt">N500</p>
        </div>
        <hr class="rule" />
        <div class="total-div">
          <p class="total-txt">TOTAL:</p>
          <p class="numb">N250,000</p>
        </div>
        <button class="btn" @click="checkOut">Proceed</button>
      </div>
    </div>
  </div>
</template>

<script>
import PaymentMethod from "../components/paymentMethod.vue";
export default {
  name: "checkout",
  data() {
    return {
      showModal: false,
      show: true,
      view: false,
      see: false,
      live: false,
    };
  },
  methods: {
    toShopping() {
      this.$router.push("/shoppingcart");
    },

    checkOut() {
      if (this.show === true) {
        this.show = false;
        this.view = true;
        this.see = false;
        this.live = true;
      } else if (this.see === false) {
        this.show = false;
        this.view = false;
        this.see = true;
        this.live = true;
      }
    },
  },
  components: { PaymentMethod },
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
  background: #f4f6fa;
  height: 100vh;
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
  width: 92%;
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
  border: 1px solid #73828f;
}

.two-txt.activeOne {
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
  border: 1px solid #73828f;
}

.three-txt.activeTwo {
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
  border: 1px solid #73828f;
}

.two-txt {
  width: 26px;
  height: 26px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  border-radius: 50%;
  text-align: center;
  background: rgba(115, 130, 143, 0.15);
  border: 1px solid #73828f;
}

.three-txt {
  width: 26px;
  height: 26px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  border-radius: 50%;
  text-align: center;
  background: rgba(115, 130, 143, 0.15);
  border: 1px solid #73828f;
}

.horizontal-rule {
  opacity: 0.1;
  border: 1px solid #f4f6fa;
  width: 100%;
  height: 0;
  margin: 13px 0 0 0;
}

.horizontal-rule.activeRule {
  opacity: 0.1;
  border: 1px solid #000000;
  width: 100%;
  height: 0;
  margin: 13px 0 0 0;
}

.horizontal-rule.activeRuler {
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
  color: #0ddf7a;
  margin: 12px 0 0 0;
}

.payment-txt.paytext {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #0ddf7a;
  margin: 12px 0 0 0;
}

.summary-txt.sumtext {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #0ddf7a;
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

.btn-outline {
  position: fixed;
  max-width: 540px;
  margin: auto auto 0 auto;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: #ffffff;
}

.bttn-div {
  display: flex;
  flex-direction: row;
  width: 92%;
  margin: 16px auto 0 auto;
  justify-content: space-between;
}

.vat-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  text-transform: uppercase;
  color: #2f2f2f;
  margin: 0 0 0 0;
  opacity: 0.6;
}

.naira-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 21px;
  text-transform: uppercase;
  color: #2f2f2f;
  margin: 0 0 0 0;
  opacity: 0.6;
}

.rule {
  border: 1px solid #dddddd;
  width: 92%;
  margin: 14px auto 0 auto;
}

.total-div {
  display: flex;
  flex-direction: row;
  width: 92%;
  margin: 19px auto 0 auto;
  justify-content: space-between;
}

.total-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  text-transform: uppercase;
  margin: 0 0 0 0;
  color: #2f2f2f;
  opacity: 0.6;
}

.numb {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 26px;
  margin: 0 0 0 0;
  color: #000000;
}

.btn {
  width: 343px;
  height: 50px;
  left: 16px;
  top: 726px;
  margin: 15px auto 36px auto;
  background: #06d6a0;
  border-radius: 3px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  text-transform: uppercase;
  color: #001845;
  display: block;
  border: none;
}
</style>