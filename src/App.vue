<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div> 

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>

  <div class="oneroom" v-for="(b,i) in 원룸들" :key="b" >
    <img :src="원룸들[i].image" class="room-img">
    <h4>{{ 원룸들[i].title }}</h4>
    <P>{{ 원룸들[i].price }}</P>

  </div>
</template>

<script>

import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){
    return {
      모달창열렸니 : false,
      메뉴들 : ['Home', 'shop', 'About'],
      신고수 : [0,0,0],
      상품들 : ['상품1', '상품2', '상품3'],
      원룸들 : data,
    }
  },
  
  methods : {
    increase(){
      this.신고수 ++;
    },
  },
}
</script>

<style>
body {
  margin : 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
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
  padding: 15px;
}
</style>
