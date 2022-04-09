<template>
<div class="menu">
  <a v-for="(test,i) in menus" :key="i" >{{test}}</a>
 
</div>
  원룸샵
  <div v-for="(products,i) in products" :key="i">
    <h4  :style="스타일" > {{products}} 원룸</h4>
    <h3  :style="스타일"></h3>
    <p>{{ price[i] }} 만원</p>
  </div>
  <div >
    <h4  :style="스타일" > {{products[0]}} 원룸</h4>
    <h3  :style="스타일"></h3>
    <p>{{ price[0] }} 만원</p>
    <button @click="increase">허위매물 신고</button>  <span> 신고수 : {{신고수}} </span>
  </div>
</template>

<script>




export default {
  name: 'App',
  data(){
    return{
      price : [60,70,80],
      신고수 : 0,
      스타일 : 'color : blue',
      logo : '원룸샵',
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      menus : ['Home', 'Shop', 'About'],

    }
  },
  methods : {
    increase() {
      this.신고수++;
    }
  },

  components: {
   
  }
}
</script>

<style>
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
</style>
