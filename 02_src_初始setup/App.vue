<template>
  <h1>一个人的信息</h1>
  <h2>姓名：{{ name }}</h2>
  <h2>年龄：{{ age }}</h2>
  <h2>性别：{{ this.sex }}</h2>
  <button @click="sayHello">点击说话</button>
  <button @click="sayWelcome">点击说话</button>
  <button @click="test1">测试一下再vue2中读取vue3中的数据何方法</button>
  <button @click="test2">测试一下再vue3中读取vue2中的数据何方法</button>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      sex:'男'
    }
  },
  methods:{
    sayWelcome(){
      alert('欢迎来到我的课堂')
    },
    test1(){
      console.log(this.sex);
      console.log(this.name);
      console.log(this.age);
      console.log(this.sayHello);
    }
  },
  setup(){
    let name = '黄弘章'
    let age = 123

    // 方法
    function sayHello(){
      alert(`我叫${name}，我${age}岁了，你好呀`)
    }
    function test2(){
      console.log(this.sex);
      console.log(this.name);
      console.log(this.age);
      console.log(this.sayHello);
    }

    return {
      name,
      age,
      sayHello,
      test2
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
