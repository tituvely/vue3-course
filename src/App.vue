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
  <div>
    <img src="./assets/room0.jpg" class="room-img" />
    <h4 @click="isModalOpen = true">{{ products[0] }}</h4>
    <p>{{ prices[0] }}만원</p>
    <button v-on:click="increase(0)">허위매물신고</button>
    <span>신고수 : {{ reportCount[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>{{ prices[1] }}만원</p>
    <button @click="increase(1)">허위매물신고</button>
    <span>신고수 : {{ reportCount[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>{{ prices[2] }}만원</p>
    <button @click="increase(2)">허위매물신고</button>
    <span>신고수 : {{ reportCount[2] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
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
