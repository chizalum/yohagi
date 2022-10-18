<template>
  <div class="full-screen">
    <div class="max-div">
      <div class="first-row">
        <div class="first-col">
          <img src="menu.svg" class="menu" alt="menu" />
        </div>
        <div class="second-col">
          <img src="yohagi.png" class="yohagi" alt="yohagi-symbol" />
          <div class="second-row">
            <p class="iyana-txt">Iyana Ipaja Market</p>
            <button class="switch-txt" @click="openModal">switch</button>
          </div>
        </div>
        <div class="third-col">
          <img src="shopping-bag.svg" class="shopping-bag" alt="shopping-bag" />
        </div>
      </div>
      <div class="third-row">
        <div class="fourth-row">
          <input
            type="search"
            class="search-bar"
            placeholder="Find Your Product"
          />
          <div class="green-box">
            <img src="sliders.svg" class="sliders" alt="sliders" />
          </div>
        </div>
        <div class="fifth-row">
          <p class="get-txt">Get 50% Off</p>
          <p class="shop-txt">SHOP WISE WITH PRICE COMPARISON</p>
          <div class="sixth-row">
            <button class="view-box" @click="productDetails">
              <p class="view-txt">VIEW COLLECTION</p>
            </button>
            <button class="category-box">
              <p class="category-txt">CATEGORIES</p>
            </button>
          </div>
        </div>
        <div class="seventh-row">
          <img
            src="watch.png"
            class="watch"
            alt="watch-img"
            @click="productDetails"
          />
          <img
            src="sweater.png"
            class="sweater"
            alt="sweater-img"
            @click="productDetails"
          />
        </div>
        <div class="top-div">
          <p class="top-txt">Top Categories This Week</p>
        </div>
        <div class="first-div">
          <p
            :class="{ activeMobile: isActiveMobile }"
            @click="activeClass()"
            class="mobile"
          >
            Mobile
          </p>
          <p
            class="headphone"
            :class="{ activeHeadphone: isActiveHeadphone }"
            @click="activateHeadphone()"
          >
            Headphone
          </p>
          <p
            class="camera"
            :class="{ activeCamera: isActiveCamera }"
            @click="activateCamera()"
          >
            Camera
          </p>
          <p
            class="drone"
            :class="{ activeDrone: isActiveDrone }"
            @click="activateDrone()"
          >
            Drone
          </p>
          <p
            class="speaker"
            :class="{ activeSpeaker: isActiveSpeaker }"
            @click="activateSpeaker"
          >
            Speaker
          </p>
        </div>
        <hr class="horizontal-rule" />
        <GridContainer v-if="showGrid"></GridContainer>
        <HeadPhone v-if="showHead"></HeadPhone>
        <Camera v-if="showCamera"></Camera>
        <Drone v-if="showDrone"></Drone>
        <Speaker v-if="showSpeaker"></Speaker>
      </div>
      <div class="fifth-div">
        <div class="sixth-div">
          <p class="hot-txt">Hot Sale</p>
          <div class="seventh-div">
            <p class="off-txt">16% Off</p>
            <p class="off-txt">25% Off</p>
            <p class="off-txt">33% Off</p>
          </div>
        </div>
        <div class="eight-div">
          <p class="basic-txt">Basic Gift Idea</p>
          <p class="mini-txt">
            Mini Two Wheel<br /><span class="span">Self Balancing Scooter</span>
          </p>
          <button class="btn-3" @click="productDetails">Go Shop</button>
        </div>
        <div class="ninth-div">
          <div
            class="deals"
            v-for="(deals, index) in dealings"
            :key="index"
            @click="productDetails"
          >
            <div class="circle-div">
              <p class="offer-txt">{{ deals.offer }}</p>
              <p class="span1">offer</p>
            </div>
            <img :src="deals.img" alt="product-image" class="laptop-img" />
            <p class="intel">{{ deals.name }}</p>
            <div class="row-div">
              <p class="first-price">{{ deals.former }}</p>
              <p class="second-price">{{ deals.current }}</p>
            </div>
            <p class="just-txt">Just {{ deals.left }} left</p>
          </div>
        </div>
      </div>
      <div class="more-div">
        <p class="more-txt">More for you</p>
      </div>
      <div class="copy-div">
        <p
          class="mobile1"
          :class="{ activetab: isActiveWomen }"
          @click="activateWomen()"
        >Women Clothing
        </p>
        <p
          class="mobile2"
          :class="{ activetab1: isActiveMen }"
          @click="activateMen()"
        >Mens Clothing
        </p>
        <p
          class="mobile3"
          :class="{ activetab2: isActivePhone }"
          @click="activateMobile()"
        >Mobile
        </p>
        <p
          class="mobile4"
          :class="{ activetab3: isActiveComputer }"
          @click="activateComputer()"
        >Computer
        </p>
        <p
          class="mobile5"
          :class="{ activetab4: isActiveSpeaker }"
          @click="activateSpeakers()"
        >Speaker
        </p>
      </div>
      <WomensCloth v-if="showWomens"></WomensCloth>
      <MensCloth v-if="showMens"></MensCloth>
      <Mobile v-if="showMobile"></Mobile>
      <Computer v-if="showComputer"></Computer>
      <SecondGrid v-if="showSecond"></SecondGrid>
    </div>
    <homeModal v-if="showModal" @closeModal="offModal()" />
  </div>
</template>
  
  <script>
import GridContainer from "~/components/gridContainer.vue";
import HeadPhone from "../components/headPhone.vue";
import Drone from "../components/drone.vue";
import Speaker from "../components/speaker.vue";
import WomensCloth from "../components/womensCloth.vue";
import MensCloth from "../components/mensCloth.vue";
import Mobile from "../components/mobile.vue";
import Computer from "../components/computer.vue";
export default {
  name: "home",
  layout: "navigation",
  computed: {
  },
  data() {
    return {
      showGrid: true,
      showHead: false,
      showCamera: false,
      showDrone: false,
      showSpeaker: false,
      showModal: false,
      showWomens: true,
      showMens: false,
      showMobile: false,
      showComputer: false,
      showSecond: false,
      showModal: false,
      isActiveMobile: true,
      isActiveHeadphone: false,
      isActiveCamera: false,
      isActiveDrone: false,
      isActiveSpeaker: false,
      isActiveMen: false,
      isActivePhone: false,
      isActiveComputer: false,
      isActiveSpeaker: false,
      isActiveWomen: true,
      dealings: [
        {
          index: 1,
          name: "Intel Laptop",
          former: "N520.00",
          current: "N499.00",
          left: "2",
          offer: "16",
          img: "laptop.png",
        },
        {
          index: 2,
          name: "Luxury Watches",
          former: "N520.00",
          current: "N540.00",
          left: "2",
          offer: "16",
          img: "new-watch.png",
        },
      ],
    };
  },
  methods: {
    productDetails() {
      this.$router.push("/productdetails");
    },
    offModal() {
      this.showModal = false;
    },
    openModal() {
      this.showModal = true;
    },
    activateMen() {
      this.isActiveMen = true;
      this.isActivePhone = false;
      this.isActiveComputer = false;
      this.isActiveSpeaker = false;
      this.isActiveWomen = false;
      this.showComputer = false;
      this.showMens = true;
      this.showWomens = false;
      this.showMobile = false;
      this.showSecond = false;
    },
    activateMobile() {
      this.isActiveMen = false;
      this.isActivePhone = true;
      this.isActiveComputer = false;
      this.isActiveSpeaker = false;
      this.isActiveWomen = false;
      this.showComputer = false;
      this.showMens = false;
      this.showWomens = false;
      this.showMobile = true;
      this.showSecond = false;
    },
    activateComputer() {
      this.isActiveMen = false;
      this.isActivePhone = false;
      this.isActiveComputer = true;
      this.isActiveSpeaker = false;
      this.isActiveWomen = false;
      this.showComputer = true;
      this.showMens = false;
      this.showWomens = false;
      this.showMobile = false;
      this.showSecond = false;
    },
    activateSpeakers() {
      this.isActiveMen = false;
      this.isActivePhone = false;
      this.isActiveComputer = false;
      this.isActiveSpeaker = true;
      this.isActiveWomen = false;
      this.showComputer = false;
      this.showMens = false;
      this.showWomens = false;
      this.showMobile = false;
      this.showSecond = true;
    },
    activateWomen() {
      this.isActiveMen = false;
      this.isActivePhone = false;
      this.isActiveComputer = false;
      this.isActiveSpeaker = false;
      this.isActiveWomen = true;
      this.showComputer = false;
      this.showMens = false;
      this.showWomens = true;
      this.showMobile = false;
      this.showSecond = false;
    },
    activeClass() {
      this.isActiveMobile = true;
      this.isActiveHeadphone = false;
      this.isActiveCamera = false;
      this.isActiveDrone = false;
      this.isActiveSpeaker = false;
      this.showGrid = true;
      this.showHead = false;
      this.showCamera = false;
      this.showDrone = false;
      this.showSpeaker = false;
    },
    activateHeadphone() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = true;
      this.isActiveCamera = false;
      this.isActiveDrone = false;
      this.isActiveSpeaker = false;
      this.showGrid = false;
      this.showHead = true;
      this.showCamera = false;
      this.showDrone = false;
      this.showSpeaker = false;
    },
    activateCamera() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = false;
      this.isActiveCamera = true;
      this.isActiveDrone = false;
      this.isActiveSpeaker = false;
      this.showGrid = false;
      this.showHead = false;
      this.showCamera = true;
      this.showDrone = false;
      this.showSpeaker = false;
    },
    activateDrone() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = false;
      this.isActiveCamera = false;
      this.isActiveDrone = true;
      this.isActiveSpeaker = false;
      this.showGrid = false;
      this.showHead = false;
      this.showCamera = false;
      this.showDrone = true;
      this.showSpeaker = false;
    },
    activateSpeaker() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = false;
      this.isActiveCamera = false;
      this.isActiveDrone = false;
      this.isActiveSpeaker = true;
      this.showGrid = false;
      this.showHead = false;
      this.showCamera = false;
      this.showDrone = false;
      this.showSpeaker = true;
    },

  },
  components: { GridContainer, HeadPhone, Drone, Speaker, WomensCloth, MensCloth, Mobile, Computer },
};
</script>
  
  <style scoped>
.full-screen {
  width: auto;
  height: auto;
  margin: 0 0 0 0;
}

.max-div {
  max-width: 540px;
  margin: 0 auto 0 auto;
}

.first-row {
  display: flex;
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.02);
  flex-direction: row;
  width: 92%;
  margin: 59px auto 0 auto;
  justify-content: start;
  padding-bottom: 13px;
}

.first-col {
  margin: 11px 0 0 0;
}

.second-col {
  margin: 0 0 0 19px;
}

.shopping-bag {
  width: 24px;
  height: 24px;
  margin: 0 0 0 0;
}

.menu {
  width: 24px;
  height: 24px;
  margin: 0 0 0 0;
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
  border: none;
  background: none;
  cursor: pointer;
}

.third-col {
  margin: 11px 0 0 auto;
}

.third-row {
  background: #ffffff;
  width: 100%;
  margin: 0 0 0 0;
}

.fourth-row {
  display: flex;
  flex-direction: row;
  width: 92%;
  margin: 0 auto 0 auto;
  justify-content: center;
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
  width: 92%;
  height: 251px;
  background: url("~assets/shopping.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
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
  background: none;
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
  justify-content: center;
}

.watch {
  width: 169px;
  height: 99px;
  margin: 0 0 0 0;
}

.sweater {
  width: 169px;
  height: 99px;
  margin: 0 0 0 5px;
}

.top-div {
  margin: 24px auto 0 auto;
}

.more-div {
  margin: 39px 0 0 0;
}

.top-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin: 0 0 0 4%;
}

.more-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin: 0 0 0 4%;
}

.copy-div {
  margin: 17px auto 0 auto;
  display: flex;
  flex-direction: row;
  overflow: scroll;
}

.first-div {
  margin: 17px auto 0 auto;
  display: flex;
  flex-direction: row;
  overflow: scroll;
}

.mobile.activeMobile {
  border-bottom: 2px solid #06d6a0;
  color: #06d6a0;
}

.headphone.activeHeadphone {
  border-bottom: 2px solid #06d6a0;
  color: #06d6a0;
}

.camera.activeCamera {
  border-bottom: 2px solid #06d6a0;
  color: #06d6a0;
}

.drone.activeDrone {
  border-bottom: 2px solid #06d6a0;
  color: #06d6a0;
}

.speaker.activeSpeaker {
  border-bottom: 2px solid #06d6a0;
  color: #06d6a0;
}

.mobile1 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 16px;
  padding-bottom: 12px;
  white-space: nowrap;
  cursor: pointer;
}

.mobile1.activetab {
  color: #06d6a0;
}

.mobile2.activetab1 {
  color: #06d6a0;
}

.mobile3.activetab2 {
  color: #06d6a0;
}

.mobile4.activetab3 {
  color: #06d6a0;
}

.mobile5.activetab4 {
  color: #06d6a0;
}

.mobile2 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 0;
  padding-bottom: 12px;
  white-space: nowrap;
  cursor: pointer;
}

.mobile3 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 0;
  padding-bottom: 12px;
  white-space: nowrap;
  cursor: pointer;
}

.mobile4 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 0;
  padding-bottom: 12px;
  white-space: nowrap;
  cursor: pointer;
}

.mobile5 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 16px;
  padding-bottom: 12px;
  white-space: nowrap;
  cursor: pointer;
}

.mobile {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 16px;
  padding-bottom: 12px;
  text-overflow: clip;
  cursor: pointer;
}

.headphone {
  font-family: "Rubik", "sans";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 0;
  padding-bottom: 12px;
  text-overflow: clip;
  cursor: pointer;
}

.camera {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 0;
  padding-bottom: 12px;
  text-overflow: clip;
  cursor: pointer;
}

.drone {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #a6a8ad;
  margin: 0 22px 0 0;
  padding-bottom: 12px;
  text-overflow: clip;
  cursor: pointer;
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
  text-overflow: clip;
  cursor: pointer;
}

.horizontal-rule {
  width: 92%;
  opacity: 0.1;
  border: 1px solid #a6a8ad;
  margin: 0 auto 0 auto;
  text-align: center;
}

.third-div {
  display: flex;
  flex-direction: row;
  width: 62px;
  height: 11px;
  justify-content: space-between;
  margin: 0 0 0 0;
}

.fifth-div {
  width: 100%;
  background: #f4f6fa;
  margin: 0 0 0 0;
  padding: 0 0 37px 0;
  display: flex;
  flex-direction: column;
}

.sixth-div {
  margin: 0 0 0 0;
  padding-top: 25px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto 0 auto;
}

.hot-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  color: #000000;
  margin: 0 18% 0 4%;
}

.off-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  color: #a6a8ad;
}

.seventh-div {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 58%;
  margin: 0 4% 0 0;
}

.eight-div {
  width: 343px;
  height: 166px;
  background: url("~assets/gift-idea.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
  margin: 22px auto 0 auto;
  display: flex;
  flex-direction: column;
}

.basic-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #001838;
  margin: 29px 0 0 24px;
}

.mini-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin: 11px 0 0 24px;
}

.span {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
}

.btn-3 {
  box-sizing: border-box;
  width: 100px;
  height: 37px;
  background: #06d6a0;
  border: none;
  border-radius: 3px;
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 10px;
  line-height: 12px;
  text-align: center;
  color: #ffffff;
  margin: 13px 0 0 24px;
}

.ninth-div {
  margin: 21px auto 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 100%;
}

.deals {
  width: 171px;
  height: 251px;
  background: #ffffff;
  text-align: center;
  margin: 0 1px 0 0;
}

.deals:hover {
  width: 201px;
  height: 251px;
}

.laptop-img {
  margin: -20px auto 0 auto;
  display: block;
}

.circle-div {
  background: #69b121;
  border-radius: 50%;
  width: 41px;
  height: 41px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  top: 9px;
  left: 122px;
  margin: 0 0 0 0;
  z-index: 999;
}

.offer-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 10px;
  line-height: 12px;
  color: #ffffff;
  text-align: center;
  margin: 0 auto 0 auto;
}

.span1 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 10px;
  line-height: 12px;
  color: #ffffff;
  text-align: center;
  margin: 0 auto 0 auto;
}

.intel {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  margin: 13px auto 0 auto;
}

.row-div {
  display: flex;
  flex-direction: row;
  margin: 9px auto 0 auto;
  justify-content: center;
  width: 100%;
}

.first-price {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  text-decoration-line: line-through;
  color: #c4c4c4;
  margin: 0 6px 0 0;
}

.second-price {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  color: #14cb73;
  margin: 0 0 0 0;
}

.just-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #bc1414;
  margin: 11px auto 0 auto;
}
</style>