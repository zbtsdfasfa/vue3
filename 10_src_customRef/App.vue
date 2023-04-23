<template>
  <input type="text" v-model="keyWord">
  <h3>{{ keyWord }}</h3>
</template>

<script>
import {ref,customRef} from 'vue'
export default {
  name: "App",
  setup(){
    // 使用vue提供的ref
    // let keyWord = ref('hello')
    // 使用自己定义的ref
    let keyWord = myRef('hello')
    let timer 
    function myRef(value){
     return customRef((track,trigger)=>{
      return {
        get(){
          console.log(`有人从myRef这个容器中读取了数据,把我${value}给他了`);
          track()
          return value
        },
        set(newvalue){
          console.log(`有人把muRef这个容器里面的数据改为了：${newvalue}`);
          clearTimeout(timer)
          timer =  setTimeout(() => {
            value = newvalue
            trigger()
          }, 500);
        }
      }
     })
    }
    return {
      keyWord
    }
  }
  
};
</script>

<style>

</style>
