<template>
  <div style="padding:15px;">
  
    <HeaderName />
    <Discount />

    <!-- <div v-for="(item, index) in products" :key="index" style="text-align:center;margin:10px;padding:10px;border-bottom:1px solid lightgray">
      <img :src="item.image" class="room-img" />
      <h2 class="room-name" v-bind:title="message" @click="openModal = true; num = index">{{item.title}}</h2>
      <p :style="inlineStyle">{{item.price}}원</p>
      <button type="button" @click="increase">허위매물 신고하기</button> <span>신고수 : {{신고수}}</span>
    </div> -->

    <Card v-bind:productOne="products[index]" v-for="(item, index) in products" :key="index" />


    <Modal v-bind:products="products" :num="num" :openModal="openModal" /> <!-- v-bind: 를 : 로 써도 됌, 좌측은 작명(par) 우측은 아래 선언된 변수명 -->

  </div>
</template>

<script>
import HeaderName from './components/Header';
import productsData from './assets/roomInfo'; //.js 생략가능
import Discount from './components/Discount';
import Modal from './components/Modal';
import Card from './components/Card';

export default {
  name: 'App',
  data(){ //data 보관함
    return {
      num : 0,
      products : productsData,    
      inlineStyle : 'align:center',
      openModal : false,
      message: "상세내용보기",
      신고수: 0,
    }
  },

  //함수 공간
  methods : {
    increase(){
      this.신고수++
    }
  },
  components: {
    HeaderName,
    Discount, //Discount : Discount 와 같음 좌우가 명칭이 같으면 한글자로 쓸 수 있음 
    Modal,
    Card : Card
  }
}
</script>

<style>
body {
  margin:0;
  font-size:0.8rem;
}
div {
  box-sizing: border-box;
}
.menu {
  padding:10px;
  background-color:darkblue;
  border-radius:10px;
  text-align:center;
}

.menu > a {
  display:inline-block;
  padding:5px;
  color:#fff
}

.room-img {
  height:100px;
}

li {
  margin-bottom:50px;
}

.black-bg {
  position:fixed;
  top:0;
  width:100%;
  height:100%;
  padding:20px;
  background:rgba(0,0,0,0.5)
}

.white-bg {
  width:100%;
  background:#fff;
  padding:20px;
  border-radius:10px;
}
</style>
