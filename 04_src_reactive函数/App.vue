<template>
  <h1>一个人的信息</h1>
  <h2>姓名：{{ person.name }}</h2>
  <h2>年龄：{{ person.age }}</h2>
  <h3>工作：{{ person.job.type }}</h3>
  <h3>工作薪水 {{ person.job.salary }}</h3>
  <h3>{{ person.job.a.b.c }}</h3>
  <h3>{{ person.hobby }}</h3>
  <button @click="changeInfo">修改人的信息</button>
</template>

<script>
import {  reactive } from "vue";
export default {
  name: "App",

  setup() {
    // let name = ref('黄弘章')
    // let age = ref(123)
    // let job = reactive({
    //   type:'前端工程师',
    //   salary:'30k',
    //   a:{
    //     b:{
    //       c:666
    //     }
    //   }
    // });
    // let hobby =  reactive(['抽烟', '喝酒','烫头'])
    let person = reactive({
      name: "黄弘章",
      age: 123,
      job: {
        salary: "30k",
        a: {
          b: {
            c: 666
          }
        },
        hobby:['抽烟', '喝酒','烫头']
      }
    });

    // 方法
    function changeInfo() {
      person.name = "刘德华";
      person.age = 55;

      // 数据改了 但是vue不会检测到  要把数据变成响应式数据
      // job.value.type = 'ui设计是'
      // job.value.salary = '60k'
      person.job.type = "后端程序员";
      person.job.salary = "40k";
      person.job.a.b.c = 999;
      person.hobby[0] = "打篮球";
    }

    return {
      person,
      changeInfo
      
    };
  }
};
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
