<template>

  <ModalVue @modalClose ="modal=false;" :onerooms="onerooms" :userClick="userClick" :modal="modal" />

  <div class="menu">
    <a v-for="(anyName, i) in menu" :key="i"> {{ anyName }}</a>
  </div>
  <DiscountVue />
  Vue랴Vue랴
  
  <CardVue @sampleName="modal = true; userClick=$event" :oneroom="onerooms[i]" v-for="(room,i) in onerooms" :key="room"/>

  <!-- <div v-for="(sample, i) in onerooms" :key="i"> -->
    <!-- <img :src="onerooms[i].image" class="room-img"> src같은 속성에 데이터 바인딩은 이런 방식으로 -->
    <!-- <h4 @click="modal = true">{{ products[i] }}</h4> -->
    <!-- <h4 @click="modal = true; userClick = i">{{ onerooms[i].title }}</h4> -->
    <!--그냥 데이터 바인딩은 {{}}-->
    <!-- {{sample}} 로 해도 동일한 결과값 출력 -->
    <!-- <p>{{ price[i] }}만원</p> -->
    <!-- <p>{{ onerooms[i].price }}만원</p> -->
    <!-- <button @click="count[i]++">허위</button> -->
    <!-- v-on:click -->
    <!-- <span>신고수 : {{ count[i] }}</span> -->
  <!-- </div> -->

</template>

<script>
import test from './assets/oneroom.js';
import DiscountVue from './Discount.vue';
import ModalVue from './Modal.vue';
import CardVue from './Card.vue';

export default {
  name: 'App',
  data() {
    return {
      userClick: 0,
      modal: false, // ui의 현재 상태(동적ui) - 사실상 모달창 스위치
      price: [50, 60, 70],
      products: ['1원룸', '2원룸', '3원룸'],
      menu: ['Home', 'Shop', 'About'],
      count: [0, 0, 0, 0, 0, 0],
      onerooms: test,
    }
  }
  /* 
  데이터 바인딩 하는 이유 : 하드 코딩하면 나중에 변경이 어렵다.
  뷰의 실시간 자동 렌더링 쓰려면 데이터 바인딩 필요. :: 그냥 data쪽 부분 바꿔주면 자동적으로 html에도 바로 적용됨
  */
  ,
  methods: {
    increase() {
      this.count += 1;
    }
  },
  components: {
    DiscountVue: DiscountVue,
    ModalVue: ModalVue,
    CardVue: CardVue,
  }
}
</script>

<style>
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
