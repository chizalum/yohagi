<template>
  <div class="full-screen">
    <div class="last-row">
      <div class="last-item" @click="home">
        <img src="grid.svg" alt="add" class="nav" />
        <nuxt-link to="home" class="nav-txt">Explore</nuxt-link>
      </div>
      <div class="last-item">
        <img src="layers.svg" alt="add" class="nav" />
        <p class="nav-txt">Categories</p>
      </div>
      <div class="last-item" @click="wishlist">
        <img :src="heart[number]" alt="add" class="nav" />
        <nuxt-link to="wishlist" class="nav-txt">Wishlist</nuxt-link>
      </div>
      <img src="profile.png" alt="profile-pic" class="profile" />
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "headerPage",

  data() {
    return {
      number: 0,
      heart: ["heart.svg", "green-heart.svg"],
    }
  },

  methods: {
  home(){
    this.$router.push("/home");
    this.number = 0;
  },

  wishlist(){
    this.$router.push("/wishlist");
    this.number = 1;
  }
}
};

</script>
  
  <style scoped>
.full-screen {
  margin: 0 auto 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 540px;
  width: 100%;
}

.last-row {
  height: 76px;
  width: 100%;
  max-width: 540px;
  background: #ffffff;
  box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.25);
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  position: fixed;
  bottom: 0;
  margin: 0 0 0 0;
  z-index: 999;
}

.last-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.nav {
  height: 18px;
  width: 18px;
  margin: 17px 0 0 0;
}

.profile {
  height: 38px;
  width: 38px;
  margin: 22px 0 0 0;
}

.nav-txt {
  font-family: "Proxima Nova";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 17px;
  color: #819bb3;
  margin: 12px 0 0 0;
  text-decoration: none;
}

a.nuxt-link-exact-active {
  font-family: "Proxima Nova";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  color: #06d6a0;
}
</style>