<template>

<div class="black-bg" v-if="modalStatus === true">
  <div class="white-bg">
    <h4>상세페이지</h4>
    <p>상세페이지 내용</p>
    <button @click="modalStatusChange">모달 닫기</button>
  </div>
  
</div>




<div class="menu">
  <a v-for="(test,i) in menus" :key="i" >{{test}}</a>
 
</div>
  원룸샵
  <div v-for="(products,i) in products" :key="i">
    <img src="./assets/groynes-4434535_1920.jpg" class ="room-img"/>
    <h4 class="RoomName" @click="modalStatusChange" :style="스타일" > {{products}} 원룸</h4>
    <h3  :style="스타일"></h3>
    <p>{{ price[i] }} 만원</p>
     <button @click="increase(i)">허위매물 신고</button>  <span> 신고수 : {{신고수[i]}} </span>
  </div>

  
</template>

<script>




export default {
  name: 'App',
  data(){
    return{
      modalStatus : false,
      price : [60,70,80],
      신고수 : [0,0,0],
      스타일 : 'color : blue',
      logo : '원룸샵',
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      menus : ['Home', 'Shop', 'About'],

    }
  },
  methods : {
    increase(index) {
      this.신고수[index]++;
    },
    modalStatusChange(){
      this.modalStatus = !this.modalStatus
    }
  },

  components: {
   
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
  width: 100%; height: 100%;
  background-color: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  widows: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
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
  padding: 16px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 300px;
  margin-top: 40px;
}
.RoomName {
  cursor: pointer;
}
</style>
