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
        <div class="grid-container">
          <div
            class="grid-item"
            v-for="(details, index) in itemsLessThanFour"
            :key="index"
          >
            <img :src="details.img" alt="product-image" class="product-image" />
            <div class="second-div">
              <img
                :src="details.heart[details.heartCurrent]"
                alt="heart"
                class="heart"
                @click="changeheart1(index)"
              />
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
        <button class="see-txt" @click="viewMore">
          <span v-if="number < 1000">See More</span>
          <span v-else>See Less</span>
        </button>
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
        >
          Women Clothing
        </p>
        <p
          class="mobile2"
          :class="{ activetab1: isActiveMen }"
          @click="activateMen()"
        >
          Mens Clothing
        </p>
        <p
          class="mobile3"
          :class="{ activetab2: isActivePhone }"
          @click="activateMobile()"
        >
          Mobile
        </p>
        <p
          class="mobile4"
          :class="{ activetab3: isActiveComputer }"
          @click="activateComputer()"
        >
          Computer
        </p>
        <p
          class="mobile5"
          :class="{ activetab4: isActiveSpeaker }"
          @click="activateSpeakers()"
        >
          Speaker
        </p>
      </div>
      <div class="second-grid">
        <div
          class="second-item"
          v-for="(details, index) in itemsLessThanSix"
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
          <div class="second-div">
            <div class="star-div">
              <img
                :src="details.star1[details.starCurrent1]"
                alt="star"
                class="star"
                @click="newStar1(index)"
              />
              <img
                :src="details.star2[details.starCurrent2]"
                alt="star"
                class="star"
                @click="newStar2(index)"
              />
              <img
                :src="details.star3[details.starCurrent3]"
                alt="star"
                class="star"
                @click="newStar3(index)"
              />
              <img
                :src="details.star4[details.starCurrent4]"
                alt="star"
                class="star"
                @click="newStar4(index)"
              />
              <img
                :src="details.star5[details.starCurrent5]"
                alt="star"
                class="star"
                @click="newStar5(index)"
              />
            </div>
            <p class="product-name1">{{ details.name }}</p>
            <div class="fourth-div1">
              <p class="previous">{{ details.previous }}</p>
              <p class="price-txt">{{ details.price }}</p>
            </div>
          </div>
          <img :src="details.plus" alt="add" class="plus" />
        </div>
      </div>
      <button class="see-txt1" @click="seeMore">
        <span v-if="secondNumber < 1000">See More</span>
        <span v-else>See Less</span>
      </button>
    </div>
    <homeModal v-if="showModal" @closeModal="offModal()" />
  </div>
</template>
  
  <script>
export default {
  name: "home",
  layout: "navigation",

  computed: {

    itemsLessThanFour: function () {
      const app = this;
      return this.packageDetails.filter(function (details) {
        return details.index <= app.number;
      });
    },

    itemsLessThanSix: function () {
      const app = this;
      return this.itemDetails.filter(function (details) {
        return details.index <= app.secondNumber;
      });
    },
  },

  data() {
    return {
      showModal: false,
      number: 4,
      secondNumber: 6,
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
      packageDetails: [
        {
          index: 1,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: "N520.00",
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
        },
        {
          index: 3,
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
        },
        {
          index: 4,
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
        },
        {
          index: 5,
          name: "Xpeed Projector",
          price: "N499.00",
          previous: null,
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
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
        {
          index: 3,
          name: "Summer Casual Cotton",
          price: "N499.00",
          previous: "N520.00",
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "secondset3.png",
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
          index: 4,
          name: "Women Tops Solid Color",
          price: "N499.00",
          previous: "N520.00",
          heart: ["heart.svg", "green-heart.svg"],
          heartCurrent: 0,
          img: "secondset4.png",
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
          index: 5,
          name: "Women Tops",
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
          index: 6,
          name: "Summer Casual Cotton",
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
        {
          index: 7,
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
          index: 8,
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
          index: 9,
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
          index: 10,
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
    },

    activateMobile() {
      this.isActiveMen = false;
      this.isActivePhone = true;
      this.isActiveComputer = false;
      this.isActiveSpeaker = false;
      this.isActiveWomen = false;
    },

    activateComputer() {
      this.isActiveMen = false;
      this.isActivePhone = false;
      this.isActiveComputer = true;
      this.isActiveSpeaker = false;
      this.isActiveWomen = false;
    },

    activateSpeakers() {
      this.isActiveMen = false;
      this.isActivePhone = false;
      this.isActiveComputer = false;
      this.isActiveSpeaker = true;
      this.isActiveWomen = false;
    },

    activateWomen() {
      this.isActiveMen = false;
      this.isActivePhone = false;
      this.isActiveComputer = false;
      this.isActiveSpeaker = false;
      this.isActiveWomen = true;
    },

    viewMore() {
      this.number = this.number === 4 ? 1000 : 4;
    },

    seeMore() {
      if (this.secondNumber <= 6) {
        this.secondNumber = 1000;
      } else {
        this.secondNumber = 6;
      }
    },

    activeClass() {
      this.isActiveMobile = true;
      this.isActiveHeadphone = false;
      this.isActiveCamera = false;
      this.isActiveDrone = false;
      this.isActiveSpeaker = false;
    },

    activateHeadphone() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = true;
      this.isActiveCamera = false;
      this.isActiveDrone = false;
      this.isActiveSpeaker = false;
    },

    activateCamera() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = false;
      this.isActiveCamera = true;
      this.isActiveDrone = false;
      this.isActiveSpeaker = false;
    },

    activateDrone() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = false;
      this.isActiveCamera = false;
      this.isActiveDrone = true;
      this.isActiveSpeaker = false;
    },

    activateSpeaker() {
      this.isActiveMobile = false;
      this.isActiveHeadphone = false;
      this.isActiveCamera = false;
      this.isActiveDrone = false;
      this.isActiveSpeaker = true;
    },

    changeheart1(index) {
      if (this.packageDetails[index].heartCurrent < 1) {
        this.packageDetails[index].heartCurrent = 1;
      } else {
        this.packageDetails[index].heartCurrent = 0;
      }
    },

    changeheart2(index) {
      if (this.itemDetails[index].heartCurrent < 1) {
        this.itemDetails[index].heartCurrent = 1;
      } else {
        this.itemDetails[index].heartCurrent = 0;
      }
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

.grid-container {
  display: grid;
  grid-template-columns: 211px 211px;
  background-color: #ffffff;
  width: 92%;
  justify-content: start;
  row-gap: 11px;
  column-gap: 6px;
  margin: 15px auto 0 auto;
  white-space: nowrap;
  overflow: scroll;
}

.second-grid {
  display: grid;
  grid-template-columns: 163px 163px;
  background-color: #ffffff;
  width: 100%;
  justify-content: space-evenly;
  row-gap: 13px;
  column-gap: 17px;
  margin: 24px auto 0 auto;
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

.grid-item {
  background: #fbfcfe;
  border: 1px solid rgba(55, 119, 177, 0.07);
  border-radius: 3px;
  height: 98px;
  width: 211px;
  display: flex;
  flex-direction: row;
  margin: 0 0 0 0;
}

.product-image {
  width: 85px;
  height: 97px;
  margin: 0 0 0 0;
}

.product-image1 {
  width: 73px;
  height: 83px;
  margin: 0 0 0 40px;
}

.second-div {
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

.third-div {
  display: flex;
  flex-direction: row;
  width: 62px;
  height: 11px;
  justify-content: space-between;
  margin: 0 0 0 0;
}

.star-div {
  display: flex;
  flex-direction: row;
  width: 62px;
  height: 11px;
  justify-content: space-between;
  margin: 0 0 0 17px;
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

.product-name1 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  color: #000000;
  margin: 7px 0 0 17px;
}

.fourth-div {
  display: flex;
  flex-direction: row;
  margin: 9px 0 0 0;
}

.fourth-div1 {
  display: flex;
  flex-direction: row;
  margin: 8px 0 0 17px;
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

.heart1 {
  width: 16px;
  height: 16px;
  margin: 10px 10px 0 auto;
}

.see-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  text-decoration-line: underline;
  color: #06d6a0;
  margin: 20px auto 28px auto;
  border: none;
  background: none;
  display: block;
  cursor: pointer;
}

.see-txt1 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  text-decoration-line: underline;
  color: #06d6a0;
  margin: 17px auto 14px auto;
  padding-bottom: 80px;
  border: none;
  background: none;
  display: block;
  cursor: pointer;
}

.fifth-div {
  width: 100%;
  background: #f4f6fa;
  margin: 0 0 0 0;
  padding: 0 0 37px 0;
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

.plus {
  width: 14px;
  height: 14px;
  background: #3b4f62;
  padding: 6px 6px 6px 6px;
  border-radius: 50%;
  margin: 2px 0 0 131px;
}
</style>