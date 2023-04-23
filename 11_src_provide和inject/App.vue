<template>
  <div class="app">
    <h3>我是app组件,{{ car.name }}---{{ car.price }}</h3>
    <child/>
  </div>
</template>

<script>
import Child from './components/Child.vue'
import { reactive,provide } from 'vue';
export default {
  name: "App",
  components:{Child},
  setup(){
    let car = reactive({
      name:'长安',
      price:'30w'
    });
    // 给自己的后代组件床底数据
    provide('car' , car)
    return{car}
  }
};
</script>

<style>
.app{
  background: pink;
  padding: 10px;
}
</style>
