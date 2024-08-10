<template>
  <div>
    <img :src="원룸.image" style="width:100%">
    <!-- <h4 @click="모달창열렸니=true ; 누른거=i">{{원룸.title}}</h4> -->
    <p>{{원룸.price}}</p>
    <p>{{원룸.content}}</p>
    <!-- <button @click="신고수[i]++">허위매물 신고</button> 
    <span>신고수 : {{신고수}}</span> -->

  </div>
</template>

<script>
export default {
    name : "cardList",
    props : {
      원룸 : Object,
    }

}
</script>

<style>

</style>