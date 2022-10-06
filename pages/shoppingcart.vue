<template>
  <div class="full-screen">
    <div class="max-div">
      <div class="first-div">
        <div class="second-div">
          <img src="bluearrow.svg" class="arrow" @click="toWish" />
          <p class="apple-txt">Shopping Cart</p>
        </div>
        <img src="share.svg" class="share" />
      </div>
      <div
        class="third-div"
        v-for="(details, index) in packageDetails"
        :key="index"
      >
        <div class="fourth-div">
          <img :src="details.img" class="image" />
          <div class="first-column">
            <p class="prod-txt">{{ details.name }}</p>
            <div class="row-div">
              <div class="minus-div" @click="subtract(index)">
                <img src="minus.svg" class="minus" />
              </div>
              <div class="num-div">{{ details.productCount }}</div>
              <div class="plus-div" @click="add(index)">
                <img src="new-plus.svg" class="new-plus" />
              </div>
            </div>
            <p class="remove" @click="remove(index)">remove</p>
          </div>
          <p class="price-count">{{ details.priceCount }}</p>
        </div>
        <hr class="horizontal-rule" />
      </div>
      <div class="fifth-div">
        <div class="sixth-div">
          <p class="vat-txt">VAT:</p>
          <p class="naira-txt">N500</p>
        </div>
        <hr class="rule" />
        <div class="seventh-div">
          <p class="total-txt">TOTAL:</p>
          <p class="numb">N250,000</p>
        </div>
        <button class="btn">Check Out</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "shoppingcart",

  data() {
    return {
      packageDetails: [
        {
          index: 1,
          name: "Headset for Phones",
          price: "N199.00",
          previous: null,
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "head-phones.png",
          star1: ["white-star.svg", "green-star.svg"],
          star2: ["white-star.svg", "green-star.svg"],
          star3: ["white-star.svg", "green-star.svg"],
          star4: ["white-star.svg", "green-star.svg"],
          star5: ["white-star.svg", "green-star.svg"],
          starCurrent1: 0,
          starCurrent2: 0,
          starCurrent3: 0,
          starCurrent4: 0,
          starCurrent5: 0,
          productCount: 1,
          priceCount: 199.0,
        },
        {
          index: 2,
          name: "Goldenhour Watch",
          price: "N60.00",
          previous: null,
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "digital-watch.png",
          star1: ["white-star.svg", "green-star.svg"],
          star2: ["white-star.svg", "green-star.svg"],
          star3: ["white-star.svg", "green-star.svg"],
          star4: ["white-star.svg", "green-star.svg"],
          star5: ["white-star.svg", "green-star.svg"],
          starCurrent1: 0,
          starCurrent2: 0,
          starCurrent3: 0,
          starCurrent4: 0,
          starCurrent5: 0,
          productCount: 1,
          priceCount: 199.0,
        },
        {
          index: 3,
          name: "Bevigac Gamepad",
          price: "N499.00",
          previous: "N499.00",
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "pad.png",
          star1: ["white-star.svg", "green-star.svg"],
          star2: ["white-star.svg", "green-star.svg"],
          star3: ["white-star.svg", "green-star.svg"],
          star4: ["white-star.svg", "green-star.svg"],
          star5: ["white-star.svg", "green-star.svg"],
          starCurrent1: 0,
          starCurrent2: 0,
          starCurrent3: 0,
          starCurrent4: 0,
          starCurrent5: 0,
          productCount: 1,
          priceCount: 199.0,
        },
      ],
    };
  },

  methods: {
   toWish(){
    this.$router.push("/wishlist");
   },

    remove(index) {
      this.packageDetails.splice(index, 1);
    },

    subtract(index) {
      if (this.packageDetails[index].productCount <= 1) {
        this.packageDetails[index].productCount = 1;
        this.packageDetails[index].priceCount = 199.0;
      } else if (this.packageDetails[index].productCount > 1) {
        this.packageDetails[index].productCount =
          this.packageDetails[index].productCount - 1;
        this.packageDetails[index].priceCount =
          this.packageDetails[index].priceCount / 2;
      }
    },

    add(index) {
      this.packageDetails[index].productCount =
        this.packageDetails[index].productCount + 1;
      this.packageDetails[index].priceCount =
        this.packageDetails[index].priceCount * 2;
    },
  },
};
</script>

<style scoped>
.body,
html {
  background: #fbfcfe;
}
.full-screen {
  width: 100%;
  height: 100%;
  margin: 0 0 0 0;
  background: #fbfcfe;
}

.max-div {
  max-width: 540px;
  margin: 0 auto 0 auto;
  background: #fbfcfe;
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

.third-div {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin: 0 0 auto 0;
  background: #fbfcfe;
}

.fourth-div {
  display: flex;
  flex-direction: row;
  width: 100%;
  margin: 0 0 0 0;
  background: #fbfcfe;
}

.image {
  width: 85px;
  height: 97px;
  margin: 15px 0 0 4%;
}

.first-column {
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
}

.prod-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  margin: 35px 0 0 0;
  color: #73828f;
}

.row-div {
  display: flex;
  flex-direction: row;
  margin: 13px 0 0 0;
}

.minus-div {
  box-sizing: border-box;
  height: 26px;
  width: 36px;
  margin: 0 0 0 0;
  background: #f4f6fa;
  border: 1px solid #dddddd;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.num-div {
  box-sizing: border-box;
  height: 26px;
  width: 36px;
  margin: 0 0 0 0;
  border: 1px solid #dddddd;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.plus-div {
  box-sizing: border-box;
  width: 36px;
  height: 26px;
  margin: 0 0 0 0;
  background: #f4f6fa;
  border: 1px solid #dddddd;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.minus {
  margin: auto auto auto auto;
}

.new-plus {
  margin: auto auto auto auto;
}

.remove {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 18px;
  text-decoration-line: underline;
  margin: 10px 0 0 0;
  color: #bc1414;
}

.price-count {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  margin: 40px 4% 0 auto;
  color: #000000;
}

.horizontal-rule {
  opacity: 0.3;
  border: 1px solid #d7d7d7;
  margin: 12px auto 0 auto;
  width: 92%;
}

.fifth-div {
  position: absolute;
  max-width: 540px;
  margin: auto auto 0 auto;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: #ffffff;
}

.sixth-div {
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

.seventh-div {
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