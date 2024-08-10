<template>

<infoModal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>

  <div class="menu">
    <a v-for="naming in menus" :key="naming">{{naming}}</a>
  </div>

<oneroomDiscount/>

<cardList :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명"/>  
  
</template>

<script>
import oneroom from "./assets/data.js";
import oneroomDiscount from "./components/oneroomDiscount.vue";
import infoModal from "./components/infoModal.vue";
import cardList from "./components/cardList.vue"

export default {
  name: 'App',
  data() {
    return {
      누른거 : 0,
      모달창열렸니: false,
      신고수: [0, 0, 0],
      menus: ['Home', 'Shop', 'About'],
      원룸들: oneroom,
      원룸: this.원룸들,
    }
  },
  methods: {
    increase() {
      this.신고수++
    },
  },
  components:{
   oneroomDiscount : oneroomDiscount,
   infoModal : infoModal,
   cardList : cardList,
    
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
