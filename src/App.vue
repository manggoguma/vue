<template>
  <!-- <div class="black-bg" v-if="모달창열렸니 === true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button class="modalClose" @click="모달창열렸니=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="naming in menus" :key="naming">{{naming}}</a>
  </div>

  <div v-for="(a,i) in 원룸들" :key="a">
    <img :src="원룸들[i].image" alt="">
    <h4 @click="모달창열렸니=true">{{원룸들[i].title}}</h4>
    <p>{{원룸들[i].price}}</p>
    <p>{{원룸들[i].content}}</p>
    <button @click="신고수[i]++">허위매물 신고</button> 
    <span>신고수 : {{신고수[i]}}</span>

  </div> -->
  
    <ShipChajang /> <!-- 컴포넌트 사용 -->
</template>

<script>
import oneroom from "./assets/data.js";
import ShipChajang from "./shipchajang.vue";

export default {
  name: 'App',
  data() {
    return {
      모달창열렸니: false,
      신고수: [0, 0, 0],
      menus: ['Home', 'Shop', 'About'],
      원룸들: oneroom,
    }
  },
  methods: {
    increase() {
      this.신고수++
    },
  },
  components: {
    ShipChajang // 컴포넌트 등록
  }
}
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5); /* rbga -> rgba */
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.modalClose {
  background: blueviolet;
  color: white;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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
</style>
