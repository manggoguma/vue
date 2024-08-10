<template>

<Transition name="fade">
  <infoModal @closeModal="모달창열렸니=false" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
</Transition>

  <div class="menu">
    <a v-for="naming in menus" :key="naming">{{naming}}</a>
  </div>

<oneroomDiscount/>

<button @click="priceSort">가격순정렬</button>
<button @click="reverseSort">가격역순정렬</button>
<button @click="koreaSort">가나다순정렬</button>
<button @click="sortBack">되돌리기</button>

<cardList @openModal="모달창열렸니=true; 누른거 = $event" 
:원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명"/>  
  
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
      원룸들오리지널 : [...oneroom], /*원룸들의 사본*/
    }
  },
  methods: {
    increase() {
      this.신고수++
    },
    priceSort(){
      this.원룸들.sort(function(a,b){
        return a.price-b.price
      })
    },
    sortBack(){
      this.원룸들=[...this.원룸들오리지널];
        
    },
    reverseSort(){
      this.원룸들.sort(function(a,b)
      {return b.price-a.price})
    },
    koreaSort(){
      this.원룸들.sort(function(a,b){
        return a.title.localeCompare(b.title)
      })
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
.fade-enter-from{
/* 시작시 스타일 */
  transform: translateY(-1000px); /* y축 이동 */
  
}
.fade-enter-active{
  transition: all 1s;

}
.fade-enter-to{
/* 끝날시 스타일 */
 transform: translateY(0px); /* y축 원상복귀 */
}

.fade-leave-from{
/* 시작시 스타일 */
  opacity: 1;
  
}
.fade-leave-active{
  transition: all 1s;

}
.fade-leave-to{
/* 끝날시 스타일 */
opacity: 0;
}
.start {
  opacity: 0;
  transition: all 1s;
}
.end{
  opacity: 1;
}

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
