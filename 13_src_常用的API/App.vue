<template>
  <div class="app">
    <h3>我是app组件</h3>
    <child/>
  </div>
</template>

<script>
import { isProxy,reactive, isReactive, isReadonly, isRef, readonly, ref } from 'vue';


export default {
  name: "App",
 
  setup(){
    let car = reactive({name:'长安',price:'30w'});
    let sum = ref(0);
    let car2 = readonly(car)

    console.log(isRef(sum));
    console.log(isReactive(car));
    console.log(isReadonly(car2));
    console.log(isProxy(car));
    return{car,sum ,car2}
  }
};
</script>

<style>
.app{
  background: pink;
  padding: 10px;
}
</style>
