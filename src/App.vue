<template>
  <div v-if="isModalOpen" class="black-bg">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>내용</p>
      <button @click="isModalOpen = false">Close</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
  <div v-for="room in rooms" :key="room">
    <img :src="room.image" class="room-img" />
    <h4>{{ room.title }}</h4>
    <p>{{ room.price }}</p>
  </div>
</template>

<script>
import rooms from "./assets/oneroom.js";

export default {
  name: "App",
  data() {
    return {
      rooms: rooms,
      isModalOpen: false,
      reportCount: [0, 0, 0],
      prices: [50, 60, 70],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Products", "About"],
    };
  },
  methods: {
    increase(index) {
      this.reportCount[index]++;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
