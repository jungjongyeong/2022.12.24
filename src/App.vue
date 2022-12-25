<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <button @click="모달창열렸니 = false">닫기</button>
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div> 

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>

  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ 상품들[0] }}</h4>
    <P>{{ price2 }}</P>
    <button @click="신고수[0]++">허위매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ 상품들[1] }}</h4>
    <P>{{ price2 }}</P>
    <button @click="신고수[1]++">허위매물신고</button> <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ 상품들[2] }}</h4>
    <P>{{ price2 }}</P>
    <button @click="신고수[2]++">허위매물신고</button> <span>신고수 : {{ 신고수[2] }}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      모달창열렸니 : false,
      메뉴들 : ['Home', 'shop', 'About'],
      신고수 : [0,0,0],
      상품들 : ['상품1', '상품2', '상품3'],
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
