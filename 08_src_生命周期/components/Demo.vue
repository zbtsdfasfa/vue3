<template>
  <h1>一个人的信息</h1>
  <h2>{{ sum }}</h2>
  <h2>{{ msg }}</h2>
</template>

<script>
import { reactive, computed, ref, watch, watchEffect } from "vue";
export default {
  name: "App",

  setup() {
    let sum = ref(0)
    let msg = ref('你好')
    return {
        sum,
        msg
    }
  },
  beforeCreate(){
    console.log('----beforeCreate----');
  },
  Create(){
    console.log('----Create----');
  },
  beforeMount(){
    console.log('----beforeMount----');
  },
  mounted(){
    console.log('----beforeCreate----');
  },
  beforeUpdate(){
    console.log('----beforeUpdate----');
  },
  updated(){
    console.log('----updated----');
  },
  beforeUnmount(){
    console.log('----beforeUnmount----');
  },
  unmounted(){
    console.log('----unmounted----');
  }
};
</script>

<style>

</style>