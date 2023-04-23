<template>
  <h1>一个人的信息</h1>
  <h2>姓名：{{ name }}</h2>
  <h2>年龄：{{ age }}</h2>
  <h3>工作：{{ job.type }}</h3>
  <h3>工作薪水 {{ job.salary }}</h3>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import {ref} from 'vue'
export default {
  name: 'App',

  setup(){
    let name = ref('黄弘章')
    let age = ref(123)
    let job = ref({
      type:'前端工程师',
      salary:'30k'
    })

    // 方法
    function changeInfo(){
      name.value = '刘德华'
      age.value =55
      // 数据改了 但是vue不会检测到  要把数据变成响应式数据
      job.value.type = 'ui设计是'
      job.value.salary = '60k'
      console.log(name,age);
      console.log(job.value);
    }


    return {
      name,
      age, 
      changeInfo,
      job
    }

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
  margin-top: 60px;
}
</style>
