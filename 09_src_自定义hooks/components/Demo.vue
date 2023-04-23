<template>
  <h1>一个人的信息</h1>
  <h2>{{ sum }}</h2>
  <h2>{{ msg }}</h2>
  <hr>
  <h2>当前点击的鼠标坐标为：x:{{ point.x }} y:{{ point.y }}</h2>
</template>

<script>
import { ref } from "vue";
import usePoint from '../hooks/usePoint'
export default {
  name: "App",

  setup() {
    let sum = ref(0)
    let msg = ref('你好')
    let point = usePoint()
     
    return {
        sum,
        msg,
        point
    }
  }
};
</script>

<style>

</style>