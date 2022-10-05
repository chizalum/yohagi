<template>
  <div class="full-screen">
    <div class="max-div">
      <div class="first-div">
        <div class="second-div">
          <img src="bluearrow.svg" class="arrow" @click="home" />
          <p class="apple-txt">Apple Macbook Pro...</p>
        </div>
        <img src="share.svg" class="share" />
      </div>
      <div class="third-div">
        <div class="fourth-div">
          <img src="casio.png" class="casio" alt="product-image" />
        </div>
        <h2 class="header-txt">
          Apple Apple IPhone X - 5.8'' - 3GB RAM + 64GB ROM - (12MP + 12MP) +
          7MP Smartphone - White
        </h2>
        <p class="olu">Oluventure Technologies</p>
        <div
          class="fifth-div"
          v-for="(details, index) in packageDetails"
          :key="index"
        >
          <img
            :src="details.star1[details.starCurrent1]"
            class="star"
            @click="changeStar1(index)"
          />
          <img
            :src="details.star2[details.starCurrent2]"
            class="star"
            @click="changeStar2"
          />
          <img
            :src="details.star3[details.starCurrent3]"
            class="star"
            @click="changeStar3"
          />
          <img
            :src="details.star4[details.starCurrent4]"
            class="star"
            @click="changeStar4"
          />
          <img
            :src="details.star5[details.starCurrent5]"
            class="star"
            @click="changeStar5"
          />
          <p class="review-txt">(120 Reviews)</p>
        </div>
        <p class="price-txt">N250,000</p>
        <div class="sixth-div">
          <p class="previous-price">N265,000</p>
          <p class="percent">-10%</p>
        </div>
      </div>
      <div class="seventh-div">
        <p class="product-txt">Product Details</p>
        <div class="eight-div">
          <p
            class="spec-txt"
            :class="{ activeSpec: isActiveSpec }"
            @click="activateSpec"
          >
            Specifications
          </p>
          <p
            class="vendor-txt"
            :class="{ activeVendor: isActiveVendor }"
            @click="activateVendor"
          >
            Vendor
          </p>
          <p
            class="reviews-txt"
            :class="{ activeReview: isActiveReview }"
            @click="activateReview"
          >
            Reviews
          </p>
        </div>
        <hr class="horizontal-rule" />
        <div class="grid-container">
          <p class="bold-txt">Screen:</p>
          <p class="content">5.8" OLED HD Retina Display</p>
          <p class="bold-txt">Memory:</p>
          <p class="content">5.8" OLED HD Retina Display</p>
          <p class="bold-txt">CPU:</p>
          <p class="content">5.8" OLED HD Retina Display</p>
          <p class="bold-txt">Operating System:</p>
          <p class="content">5.8" OLED HD Retina Display</p>
          <p class="bold-txt">Camera:</p>
          <p class="content">
            12MP wide-angle and telephoto cameras, 7MP TrueDepth front camera
          </p>
          <p class="bold-txt">Battery:</p>
          <p class="content">Up to 21 hours talk time</p>
          <p class="bold-txt">Support:</p>
          <p class="content">Face ID, Siri, NFC, wireless charge</p>
        </div>
      </div>
      <div class="ninth-div">
        <p class="similar-txt">Similar Products</p>
        <div class="second-grid">
          <div
            class="second-item"
            v-for="(details, index) in itemDetails"
            :key="index"
          >
            <div class="heart-div">
              <img
                :src="details.img"
                alt="product-image"
                class="product-image1"
              />
              <img
                alt="heart"
                :src="details.heart[details.heartCurrent]"
                class="heart1"
                @click="changeheart2(index)"
              />
            </div>
            <div class="new-div">
              <div class="star-div">
                <img
                  :src="details.star1[details.starCurrent1]"
                  alt="star"
                  class="staring"
                  @click="newStar1(index)"
                />
                <img
                  :src="details.star2[details.starCurrent2]"
                  alt="star"
                  class="staring"
                  @click="newStar2(index)"
                />
                <img
                  :src="details.star3[details.starCurrent3]"
                  alt="star"
                  class="staring"
                  @click="newStar3(index)"
                />
                <img
                  :src="details.star4[details.starCurrent4]"
                  alt="star"
                  class="staring"
                  @click="newStar4(index)"
                />
                <img
                  :src="details.star5[details.starCurrent5]"
                  alt="star"
                  class="staring"
                  @click="newStar5(index)"
                />
              </div>
              <p class="product-name1">{{ details.name }}</p>
              <div class="fourth-divide">
                <p class="previous-detail">{{ details.previous }}</p>
                <p class="price-text">{{ details.price }}</p>
              </div>
            </div>
            <img :src="details.plus" alt="add" class="plus" />
          </div>
        </div>
      </div>
      <div class="tenth-div" v-if="yes">
        <div class="flex-div">
          <div class="row-div">
            <div class="minus-div" @click="subtract">
              <img src="minus.svg" class="minus" />
            </div>
            <div class="num-div">{{ productCount }}</div>
            <div class="plus-div" @click="add">
              <img src="new-plus.svg" class="new-plus" />
            </div>
          </div>
          <div class="naira-row">
            <p class="naira">N</p>
            <p class="price-count">{{ priceCount }}</p>
          </div>
        </div>
        <div class="btn-flex">
          <button class="button" @click="changeIf">ADD TO CART</button>
          <div class="heart-container" @click="changeColor">
            <img class="white-heart" :src="heart[heartCount]" />
          </div>
        </div>
      </div>
      <div v-else class="tenth-div">
        <div class="btn-flex">
          <button class="button">VIEW CART</button>
          <div class="heart-container" @click="changeColor">
            <img class="white-heart" :src="heart[heartCount]" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "productdetails",
  layout: "default",
  data() {
    return {
      yes: true,
      heartCount: 0,
      productCount: 1,
      priceCount: 250000,
      isActiveSpec: true,
      isActiveVendor: false,
      isActiveReview: false,
      heart: ["white-heart.svg", "green-heart.svg"],
      itemDetails: [
        {
          index: 1,
          name: "Women Tops Solid Color",
          price: "N499.00",
          previous: "N520.00",
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "secondset1.png",
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
          plus: "plus.svg",
        },
        {
          index: 2,
          name: "Women Tops",
          price: "N499.00",
          previous: "N520.00",
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "secondset2.png",
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
          plus: "plus.svg",
        },
      ],
      packageDetails: [
        {
          star1: ["white-star.svg", "gold-star.svg"],
          star2: ["white-star.svg", "gold-star.svg"],
          star3: ["white-star.svg", "gold-star.svg"],
          star4: ["white-star.svg", "gold-star.svg"],
          star5: ["white-star.svg", "gold-star.svg"],
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
   home(){
    this.$router.push("/home");
   },

    changeIf() {
      this.yes = false;
    },

    changeColor() {
      if (this.heartCount < 1) {
        this.heartCount = 1;
      } else {
        this.heartCount = 0;
      }
    },

    subtract() {
      if (this.productCount <= 1) {
        this.productCount = 1;
        this.priceCount = 250000;
      } else if (this.productCount > 1) {
        this.productCount = this.productCount - 1;
        this.priceCount = this.priceCount / 2;
      }
    },

    add() {
      this.productCount = this.productCount + 1;
      this.priceCount = this.priceCount * 2;
    },

    activateSpec() {
      this.isActiveSpec = true;
      this.isActiveVendor = false;
      this.isActiveReview = false;
    },
    activateVendor() {
      this.isActiveSpec = false;
      this.isActiveVendor = true;
      this.isActiveReview = false;
    },
    activateReview() {
      this.isActiveSpec = false;
      this.isActiveVendor = false;
      this.isActiveReview = true;
    },

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
        this.packageDetails[index].starCurrent2 = 0;
        this.packageDetails[index].starCurrent3 = 0;
        this.packageDetails[index].starCurrent4 = 0;
        this.packageDetails[index].starCurrent5 = 0;
      }
    },

    newStar1(index) {
      if (this.itemDetails[index].starCurrent1 < 1) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent5 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent4 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent3 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent2 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else {
        this.itemDetails[index].starCurrent1 = 0;
      }
    },

    newStar2(index) {
      if (this.itemDetails[index].starCurrent2 < 1) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent5 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent4 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent3 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else {
        this.itemDetails[index].starCurrent1 = 0;
        this.itemDetails[index].starCurrent2 = 0;
      }
    },

    newStar3(index) {
      if (this.itemDetails[index].starCurrent3 < 1) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 1;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent5 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 1;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent4 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 1;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      } else {
        this.itemDetails[index].starCurrent1 = 0;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
      }
    },

    newStar4(index) {
      if (this.itemDetails[index].starCurrent4 < 1) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 1;
        this.itemDetails[index].starCurrent4 = 1;
        this.itemDetails[index].starCurrent5 = 0;
      } else if (this.itemDetails[index].starCurrent5 > 0) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 1;
        this.itemDetails[index].starCurrent4 = 1;
        this.itemDetails[index].starCurrent5 = 0;
      } else {
        this.itemDetails[index].starCurrent1 = 0;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
      }
    },

    newStar5(index) {
      if (this.itemDetails[index].starCurrent5 < 1) {
        this.itemDetails[index].starCurrent1 = 1;
        this.itemDetails[index].starCurrent2 = 1;
        this.itemDetails[index].starCurrent3 = 1;
        this.itemDetails[index].starCurrent4 = 1;
        this.itemDetails[index].starCurrent5 = 1;
      } else {
        this.itemDetails[index].starCurrent1 = 0;
        this.itemDetails[index].starCurrent2 = 0;
        this.itemDetails[index].starCurrent3 = 0;
        this.itemDetails[index].starCurrent4 = 0;
        this.itemDetails[index].starCurrent5 = 0;
      }
    },
  },
};
</script>
  
  <style scoped >
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
  width: 100%;
  margin: 0 auto 0 auto;
  background: #e5e5e5;
  padding: 8px 0 17px 0;
}

.fourth-div {
  background: linear-gradient(0deg, #f4f3f9, #f4f3f9);
  width: 92%;
  margin: 22px auto 0 auto;
}

.casio {
  width: 132px;
  height: 151px;
  margin: 0 auto 0 auto;
  display: block;
}

.header-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 26px;
  color: #000000;
  margin: 31px 4% 0 4%;
}

.olu {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  margin: 12px 0 0 4%;
  color: #073f74;
}

.fifth-div {
  display: flex;
  flex-direction: row;
  margin: 11px 0 0 4%;
  width: auto;
}

.star {
  margin: 0 2px 0 0;
}

.review-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  margin: 0 0 0 5px;
  color: #979dac;
}

.price-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 26px;
  margin: 16px 0 0 4%;
  color: #000000;
}

.sixth-div {
  margin: 9px 0 0 4%;
  display: flex;
  flex-direction: row;
}

.previous-price {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  text-decoration-line: line-through;
  margin: 0 13px 0 0;
  color: #c4c4c4;
}

.percent {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  margin: 0 0 0 0;
  color: #bc1414;
  background: rgba(237, 178, 123, 0.5);
  border-radius: 2px;
}

.seventh-div {
  width: 100%;
  margin: 0 0 0 0;
  padding: 23px 0 26px 0;
}
.product-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  margin: 0 0 0 4%;
  color: #000000;
}

.eight-div {
  display: flex;
  flex-direction: row;
  width: 92%;
  margin: 17px auto 0 auto;
  justify-content: space-between;
}

.spec-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  padding-bottom: 12px;
  cursor: pointer;
  margin: 0 0 0 0;
}

.vendor-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  padding-bottom: 12px;
  cursor: pointer;
  margin: 0 0 0 0;
}

.reviews-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  padding-bottom: 12px;
  cursor: pointer;
  margin: 0 0 0 0;
}

.activeSpec.spec-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #06d6a0;
  border-bottom: 2px solid #06d6a0;
}

.activeVendor.vendor-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #06d6a0;
  border-bottom: 2px solid #06d6a0;
}

.activeReview.reviews-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #06d6a0;
  border-bottom: 2px solid #06d6a0;
}

.horizontal-rule {
  opacity: 0.1;
  border: 1px solid #a6a8ad;
  width: 92%;
  margin: 0 auto 0 auto;
  text-align: center;
}

.grid-container {
  display: grid;
  grid-template-columns: 21% 67%;
  background-color: #ffffff;
  width: 92%;
  justify-content: start;
  row-gap: 20px;
  column-gap: 4%;
  margin: 18px auto 0 auto;
}

.bold-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin: 0 0 0 0;
}

.content {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #7d8597;
  margin: 0 0 0 0;
}

.second-grid {
  display: grid;
  grid-template-columns: 163px 163px;
  width: 100%;
  justify-content: space-evenly;
  row-gap: 13px;
  column-gap: 17px;
  margin: 21px auto 0 auto;
  white-space: nowrap;
}

.second-item {
  background: #fbfcfe;
  border: 1px solid rgba(55, 119, 177, 0.07);
  border-radius: 3px;
  height: 167px;
  width: 163px;
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
}

.product-image1 {
  width: 73px;
  height: 83px;
  margin: 0 0 0 40px;
}

.new-div {
  display: flex;
  flex-direction: column;
  margin: 0 0 0 0;
  width: 100%;
}

.heart-div {
  margin: 0 0 0 0;
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: flex-start;
}

.star-div {
  display: flex;
  flex-direction: row;
  width: 62px;
  height: 11px;
  justify-content: space-between;
  margin: 0 0 0 17px;
}

.staring {
  margin: 0 0 0 0;
}

.product-name1 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  color: #000000;
  margin: 7px 0 0 17px;
}

.fourth-divide {
  display: flex;
  flex-direction: row;
  margin: 8px 0 0 17px;
}

.previous-detail {
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

.price-text {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 12px;
  line-height: 14px;
  color: #14cb73;
  margin: 0 0 0 0;
}

.heart1 {
  width: 16px;
  height: 16px;
  margin: 10px 10px 0 auto;
}

.plus {
  width: 14px;
  height: 14px;
  background: #3b4f62;
  padding: 6px 6px 6px 6px;
  border-radius: 50%;
  margin: 2px 0 0 131px;
}

.ninth-div {
  padding: 24px 0 29px 0;
  width: 100%;
  margin: 0 0 0 0;
  background: #e5e5e5;
}

.similar-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  margin: 24px 0 0 4%;
  color: #000000;
}

.tenth-div {
  padding: 31px 0 30px 0;
  margin: 0 0 0 0;
  width: 100%;
}

.flex-div {
  width: 92%;
  display: flex;
  flex-direction: row;
  margin: 0 auto 0 auto;
  justify-content: space-between;
}

.row-div {
  display: flex;
  flex-direction: row;
  margin: 0 0 0 0;
}

.minus-div {
  box-sizing: border-box;
  height: 44px;
  width: 61px;
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
  height: 44px;
  width: 61px;
  margin: 0 0 0 0;
  border: 1px solid #dddddd;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.plus-div {
  box-sizing: border-box;
  width: 61px;
  height: 44px;
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

.price-count {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 26px;
  margin: 0 0 0 0;
  color: #000000;
  align-self: center;
  overflow-wrap: break-word;
  word-break: break-word;
}

.naira-row {
  display: flex;
  flex-direction: row;
  margin: 0 0 0 0;
}

.naira {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 22px;
  line-height: 26px;
  margin: 0 0 0 0;
  color: #000000;
  align-self: center;
}

.btn-flex {
  display: flex;
  flex-direction: row;
  margin: 28px auto 0 auto;
  width: 92%;
  justify-content: space-between;
}

.button {
  background: #06d6a0;
  border-radius: 3px;
  height: 50px;
  width: 269px;
  border-radius: 3px;
  margin: 0 0 0 0;
  border: none;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  text-transform: uppercase;
  color: #001845;
}

.heart-container {
  height: 50px;
  width: 65px;
  border-radius: 3px;
  background: rgba(27, 27, 27, 0.13);
  border-radius: 3px;
  border: none;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.white-heart {
  height: 18.350000381469727px;
  width: 20px;
}
</style>