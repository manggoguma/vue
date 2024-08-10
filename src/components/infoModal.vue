<template>
    <div class="black-bg" v-if="모달창열렸니 === true"> // modal
    <div class="white-bg">
    <img :src="원룸들[누른거].image" alt="" style="width:100%">
      <h4>{{원룸들[누른거].title}}</h4>
      <p>{{원룸들[누른거].price}}원</p>
      <p>{{원룸들[누른거].content}}</p>
      <oneroomDiscount/>
      <!-- <button class="modalClose" @click="모달창열렸니=false">닫기</button> -->
    </div>
  </div>
</template>

<script>


export default {
 name : "infoModal",
 props : {
    원룸들 : Object,
    누른거 : Number ,
    모달창열렸니 :Boolean,
 }
}
</script>

<style>
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
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
</style>