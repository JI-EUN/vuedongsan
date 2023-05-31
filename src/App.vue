<template>
  <Modal :rommdata="rommdata" :clickNum="clickNum" :modalshow="modalshow"/>
  <div class="menu">
    <a v-for="(Links,i) in menu" :key="i" href="">{{ Links }}</a>
  </div>

  <Discount />


  <div v-for="(lists, i) in rommdata" :key="i">
    <img :src="lists.image" alt="">
    <h4 @click="modal(i)">{{ lists.title }}</h4>
    <p>{{ lists.price }}원</p>
    <!-- <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ count[i] }}</span> -->
  </div>
</template>

<script>
import data from './assets/data';
import Discount from './Discount';
import Modal from './Modal';

export default {
  name: 'App',
  //데이터 보관함 (중요 변수들)
  data(){
    return{
      clickNum :0,
      rommdata: data,
      modalshow:false,
      count:[0,0,0],
      price1 : 80,
      price2: 70,
      menu:['Home','Shop','About'],
      products:['역삼동 원룸', '천호동 원룸', '중구 원룸']
    }
  },  
  methods:{
    increase(i){
      this.count[i]++
    },
    modal(i){
      this.clickNum = i
      if(this.modalshow){
        this.modalshow = false;
      }else{
        this.modalshow = true;
      }
    }
  },
  components: {
    Discount,
    Modal
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
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 
img{
  max-width: 100%;
}
.discount{
  background: #eee;
  padding:10px;
  margin:10px;;
  border-radius : 5px;
}
.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}
</style>
