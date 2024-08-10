<template>
    <div class="black-bg" v-if="모달창열렸니 === true"> // modal
    <div class="white-bg">
    <img :src="원룸들[누른거].image" alt="" style="width:100%">
      <h4>{{원룸들[누른거].title}}</h4>
      <p>{{원룸들[누른거].content}}</p>
      <input @input="month=$event.target.value"/>
      <input type="range" min="1" max="12"/>
      <p>{{원룸들[누른거].price *month}}원</p>
      
      
      <button class="modalClose" @click="close">닫기</button>
    </div>
  </div>
</template>

<script>


export default {
 name : "infoModal",
 data(){
return {
  month : 1,
}
 },
watch :{
  // month(a){
  //   // 사용자가 month에 입력한 데이터가 13보다 크면 경고문 띄우기
  //   if(a>=13){
  //     alert('입력할 수 있는 숫자를 초과하였습니다')
  //   }
  // }

  // 사용자가 month에 글자를 입력하면 alert() 띄우기, month를 1로 되돌리기 //
  month(a){
 if(isNaN(a)==true){
  alert('숫자만 입력하세요');
  this.month=1;}
  if(a>=13){
    alert('입력할 수 있는 숫자를 초과하였습니다')
  }
 }
  
},

 props : {
    원룸들 : Object,
    누른거 : Number ,
    모달창열렸니 :Boolean,
 },
 methods: {
 close(){
    this.$emit('closeModal')
 }
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