<template>
  <h1>一个人的信息</h1>
  <h2>{{ sum }}</h2>
  <h2>{{ msg }}</h2>
  <button @click="sum++">加</button>
  <button @click="msg+=`~`">jia</button>
  <button @click="person.firstName+= '1'">加1</button>
  <button @click="person.lastName+= '1'">减1</button>
  <button @click="person.job.j1 += '2'">jia2
  </button>
</template>

<script>
import { reactive, computed, ref, watch, watchEffect } from "vue";
export default {
  name: "App",

  setup() {
    let sum = ref(0)
    let msg = ref('你好')
    let person = reactive({
      firstName: "张",
      lastName:'三',
      job:{
        j1:'前端开发'
      }
    });
    //watchEffect所指定的回调中用到的数据只要发生变化，则直接重新执行回调。
    watchEffect(()=>{
      const x1 = sum.value;
      const x2 = person.job.j1
      console.log('watchEffecr配置回调执行了');
    })
    return {
        person,
        sum,
        msg
    }
  }
};
</script>

<style>

</style>