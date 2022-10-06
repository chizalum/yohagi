<template>
  <div class="full-screen">
    <div class="max-div">
      <div class="first-div">
        <p class="wish-txt">My wishlist</p>
        <img src="share.svg" class="share" />
      </div>
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
      <button class="btn">
        <span class="add-txt" @click="toCart">Add To Cart</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "wishlist",
  layout: "navigation",
  data() {
    return {
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
    };
  },

  methods: {
   toCart(){
    this.$router.push("/shoppingcart");
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

.product-name1 {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  color: #000000;
  margin: 7px 0 0 17px;
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

.first-div {
  margin: 26px 0 0 0;
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.wish-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  color: #001845;
  margin: 0 0 0 4%;
}

.share {
  width: 24px;
  height: 24px;
  margin: 0 4% 0 0;
}

.btn {
  width: 343px;
  height: 50px;
  background: #06d6a0;
  border-radius: 3px;
  cursor: pointer;
  margin: 0 auto 100px auto;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translate(-50%, 0);
  display: block;
  border: none;
}

.add-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 17px;
  text-align: center;
  text-transform: uppercase;
  color: #001845;
}
</style>