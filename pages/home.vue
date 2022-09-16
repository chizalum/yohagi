<template>
  <div class="full-screen">
    <div class="first-row">
      <div class="first-col">
        <img src="menu.svg" class="menu" alt="menu" />
      </div>
      <div class="second-col">
        <img src="yohagi.png" class="yohagi" alt="yohagi-symbol" />
        <div class="second-row">
          <p class="iyana-txt">Iyana Ipaja Market</p>
          <p class="switch-txt">switch</p>
        </div>
      </div>
      <div class="third-col">
        <img src="shopping-bag.svg" class="shopping-bag" alt="shopping-bag" />
      </div>
    </div>
    <div class="third-row">
      <div class="fourth-row">
        <input type="text" class="search-bar" placeholder="Find Your Product" />
        <div class="green-box">
          <img src="sliders.svg" class="sliders" alt="sliders" />
        </div>
      </div>
      <div class="fifth-row">
        <p class="get-txt">Get 50% Off</p>
        <p class="shop-txt">SHOP WISE WITH PRICE COMPARISONS</p>
        <div class="sixth-row">
          <div class="view-box">
            <p class="view-txt">VIEW COLLECTION</p>
          </div>
          <div class="category-box">
            <p class="category-txt">CATEGORIES</p>
          </div>
        </div>
      </div>
      <div class="seventh-row">
        <img src="watch.png" class="watch" alt="watch-img" />
        <img src="sweater.png" class="sweater" alt="sweater-img" />
      </div>
      <div class="top-div">
        <p class="top-txt">Top Categories This Week</p>
      </div>
      <div class="first-div">
        <p class="mobile">Mobile</p>
        <p class="headphone">Headphone</p>
        <p class="camera">Camera</p>
        <p class="drone">Drone</p>
        <p class="speaker">Speaker</p>
      </div>
      <hr class="horizontal-rule" />
      <div class="grid-container">
        <div
          class="grid-item"
          v-for="(details, index) in packageDetails"
          :key="index"
        >
          <img :src="details.img" alt="product-image" class="product-image" />
          <div class="second-div">
            <img :src="details.heart" alt="heart" class="heart" />
            <div class="third-div">
              <img
                :src="details.star1[details.starCurrent1]"
                alt="star"
                class="star"
                @click="changeStar1(index)"
              />
              <img
                :src="details.star2[details.starCurrent2]"
                alt="star"
                class="star"
                @click="changeStar2(index)"
              />
              <img
                :src="details.star3[details.starCurrent3]"
                alt="star"
                class="star"
                @click="changeStar3(index)"
              />
              <img
                :src="details.star4[details.starCurrent4]"
                alt="star"
                class="star"
                @click="changeStar4(index)"
              />
              <img
                :src="details.star5[details.starCurrent5]"
                alt="star"
                class="star"
                @click="changeStar5(index)"
              />
            </div>
            <p class="product-name">{{ details.name }}</p>
            <div class="fourth-div">
              <p class="previous">{{ details.previous }}</p>
              <p class="price-txt">{{ details.price }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "home",
  layout: "default",

  data() {
    return {
      packageDetails: [
        {
          index: 1,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: "N520.00",
          heart: "heart.svg",
          img: "projector.png",
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
        },
        {
          index: 2,
          name: "Bevigac Gamepad",
          price: "N499.00",
          previous: "N499.00",
          heart: "heart.svg",
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
        },
        {
          index: 3,
          name: "Headset for Phones",
          price: "N199.00",
          previous: null,
          heart: "heart.svg",
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
        },
        {
          index: 4,
          name: "Goldenhour Watch",
          price: "N60.00",
          previous: null,
          heart: "heart.svg",
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
        },
        {
          index: 5,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: "heart.svg",
          img: "projector.png",
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
        },
        {
          index: 6,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: "heart.svg",
          img: "projector.png",
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
        },
        {
          index: 7,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: "heart.svg",
          img: "projector.png",
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
        },
        {
          index: 8,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: "heart.svg",
          img: "projector.png",
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
        },
        {
          index: 9,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: "heart.svg",
          img: "projector.png",
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
        },
        {
          index: 10,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: "heart.svg",
          img: "projector.png",
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
        },
      ],
    };
  },

  methods: {
    changeStar1(index) {
      if (this.packageDetails[index].starCurrent1 < 1) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent5 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent4 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent3 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent2 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else {
        this.packageDetails[index].starCurrent1 = 0;
      }
    },

    changeStar2(index) {
      if (this.packageDetails[index].starCurrent2 < 1) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent5 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent4 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent3 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else {
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent2 = 0;
      }
    },

    changeStar3(index) {
      if (this.packageDetails[index].starCurrent3 < 1) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 1;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent5 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 1;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent4 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 1;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      } else {
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
      }
    },

    changeStar4(index) {
      if (this.packageDetails[index].starCurrent4 < 1) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 1;
        this.packageDetails[index].starCurrent4 = 1;
        this.packageDetails[index].starCurrent5 = 0;
      } else if (this.packageDetails[index].starCurrent5 > 0) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 1;
        this.packageDetails[index].starCurrent4 = 1;
        this.packageDetails[index].starCurrent5 = 0;
      } else {
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
      }
    },

    changeStar5(index) {
      if (this.packageDetails[index].starCurrent5 < 1) {
        this.packageDetails[index].starCurrent1 = 1;
        this.packageDetails[index].starCurrent2 = 1;
        this.packageDetails[index].starCurrent3 = 1;
        this.packageDetails[index].starCurrent4 = 1;
        this.packageDetails[index].starCurrent5 = 1;
      } else {
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent1 = 0;
        this.packageDetails[index].starCurrent1 = 0;
      }
    },
  }
};
</script>
  
  <style scoped>
.full-screen {
  width: 100%;
  max-width: 768px;
  min-height: 700px;
  height: 100vh;
  margin: 0 auto 0 auto;
}

.first-row {
  display: flex;
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.02);
  flex-direction: row;
  width: 100%;
  margin: 59px 0 0 0;
  justify-content: start;
  padding-bottom: 13px;
}

.first-col {
  margin: 11px 0 0 16px;
}

.second-col {
  margin: 0 0 0 19px;
}

.yohagi {
  margin: 0 0 0 0;
  width: 91px;
  height: 23px;
}

.second-row {
  display: flex;
  flex-direction: row;
  margin: 8px 0 0 0;
  padding: 0;
}

.iyana-txt {
  padding: 0;
  margin: 0 0 0 0;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 18px;
  color: #7d8597;
}

.switch-txt {
  padding: 0;
  margin: 0 0 0 8px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 18px;
  text-decoration-line: underline;
  color: #0ddf7a;
}

.third-col {
  margin: 0 16px 0 auto;
}

.third-row {
  background: #ffffff;
  width: 100%;
  margin: 0 0 0 0;
  padding: 0 16px 0 16px;
}

.fourth-row {
  display: flex;
  flex-direction: row;
  width: fit-content;
  margin: 0 auto 0 auto;
}

.search-bar {
  box-sizing: border-box;
  width: 287px;
  height: 48px;
  border: 1px solid #73828f;
  border-radius: 3px;
  margin: 21px 0 0 0;
  padding-left: 54px;
}

.search-bar::placeholder {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #73828f;
}

.green-box {
  box-sizing: border-box;
  min-width: 49px;
  width: 49px;
  height: 48px;
  background: rgba(6, 214, 160, 0.18);
  border: 1px solid #06d6a0;
  border-radius: 3px;
  transform: matrix(-1, 0, 0, 1, 0, 0);
  margin: 21px 0 0 7px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.fifth-row {
  width: 375px;
  height: 251px;
  background: url("~assets/shopping.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
  margin: 22px auto 0 auto;
}

.get-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #ffffff;
  padding: 76px 0 0 38px;
}

.shop-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 24px;
  color: #ffffff;
  margin: 8px 0 0 38px;
}

.sixth-row {
  display: flex;
  flex-direction: row;
  width: 100%;
}

.view-box {
  box-sizing: border-box;
  width: 123px;
  height: 37px;
  border: 1px solid #f5f8ff;
  border-radius: 3px;
  margin: 26px 8px 0 38px;
}

.view-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 10px;
  line-height: 12px;
  text-align: center;
  color: #f5f8ff;
}

.category-box {
  box-sizing: border-box;
  width: 123px;
  height: 37px;
  background: #06d6a0;
  border: none;
  margin: 26px 0 0 0;
}

.category-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 10px;
  line-height: 12px;
  text-align: center;
  color: #000000;
}

.seventh-row {
  display: flex;
  flex-direction: row;
  width: fit-content;
  margin: 20px auto 0 auto;
}

.watch {
  width: 169px;
  height: 99px;
  margin: 0 0 0 0;
}

.sweater {
  width: 169px;
  height: 99px;
  margin: 0 0 0 37px;
}

.top-div {
  margin: 24px auto 0 auto;
  width: 375px;
}

.top-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
}

.first-div {
  margin: 17px auto 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
}

.mobile {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  padding-bottom: 12px;
}

.headphone {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  padding-bottom: 12px;
}

.camera {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  padding-bottom: 12px;
}

.drone {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  padding-bottom: 12px;
}

.speaker {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 0 0 0;
  padding-bottom: 12px;
}

.horizontal-rule {
  width: 92%;
  opacity: 0.1;
  border: 1px solid #a6a8ad;
  margin: 0 auto 0 auto;
  text-align: center;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, 211px);
  background-color: #ffffff;
  width: 100%;
  justify-content: space-evenly;
  row-gap: 11px;
  margin: 15px 0 0 0;
}

.grid-item {
  background: #fbfcfe;
  border: 1px solid rgba(55, 119, 177, 0.07);
  border-radius: 3px;
  height: 98px;
  width: 211px;
  display: flex;
  flex-direction: row;
}

.product-image {
  width: 85px;
  height: 97px;
  margin: 0 0 0 0;
}

.second-div {
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
  width: 100%;
}

.third-div {
  display: flex;
  flex-direction: row;
  width: 62px;
  height: 11px;
  justify-content: space-between;
  margin: 0 0 0 0;
}

.star {
  margin: 0 0 0 0;
}

.product-name {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  color: #000000;
  margin: 7px 0 0 0;
}

.fourth-div {
  display: flex;
  flex-direction: row;
  margin: 9px 0 0 0;
}

.previous {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 12px;
  line-height: 14px;
  text-decoration-line: line-through;
  color: #c4c4c4;
  margin: 0 0 0 0;
  padding-right: 6px;
}

.price-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 12px;
  line-height: 14px;
  color: #14cb73;
  margin: 0 0 0 0;
}

.heart {
  width: 16px;
  height: 16px;
  align-self: flex-end;
  margin: 7.8px 8.3px 0 0;
}
</style>