<template>
  <div style="text-align:center;margin:10px;padding:10px;border-bottom:1px solid lightgray">
      <img :src="productOne.image" class="room-img" />
      <h2 class="room-name">{{productOne.title}}</h2><!-- @click="openModal = true; num = index" -->
      <p>{{productOne.price}}원</p>
      <!-- <button type="button" @click="increase">허위매물 신고하기</button> <span>신고수 : {{신고수}}</span> -->
    </div>
</template>

<script>
export default {
  name: "Card-name",
  props : {
        productOne: Object,
    }
}
</script>

<style>
.room-name:hover {
  color:blueviolet;
  cursor:pointer;
}
</style>