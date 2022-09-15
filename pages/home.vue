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
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "home",
  layout: "default",
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
  margin: 0 22.7px 0 auto;
}

.third-row {
  background: #ffffff;
  width: 100%;
  margin: 0 0 0 0;
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

.top-div{
  margin: 24px auto 0 auto;
  width: 375px
}

.top-txt {
  font-family: "Rubik";
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
}
</style>