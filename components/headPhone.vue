<template>
    <div>
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
  </template>
  
  <script>
  export default {
  name: 'headPhone',
  
  computed: {
  itemsLessThanFour: function () {
    const app = this;
    return this.packageDetails.filter(function (details) {
      return details.index <= app.number;
    });
  },
  },
  
  
  data(){
      return{
          number: 4,
          packageDetails: [
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
        ],
      }
  },
  
  methods:{
      changeheart1(index) {
        if (this.packageDetails[index].heartCurrent < 1) {
          this.packageDetails[index].heartCurrent = 1;
        } else {
          this.packageDetails[index].heartCurrent = 0;
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
  
      viewMore() {
        this.number = this.number === 4 ? 1000 : 4;
      },
  },
  }
  </script>
  
  <style scoped>
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
  
  .second-div {
    display: flex;
    flex-direction: column;
    margin: 0 0 0 0;
    width: 100%;
  }
  
  .heart {
    width: 16px;
    height: 16px;
    align-self: flex-end;
    margin: 7.8px 8.3px 0 0;
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
  </style>