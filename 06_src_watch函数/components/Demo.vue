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
import { reactive, computed, ref, watch } from "vue";
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
    // 情况一：监视ref定义的响应式数据
    // watch(sum ,(newValue,oldValue)=>{
    //   console.log('sum改变了',newValue,oldValue);
    // })

    //情况二：监视多个ref定义的响应式数据
    // watch([sum,msg],(newValue,oldValue)=>{
    //   console.log('sum或者msg变化了' ,newValue,oldValue);
    // })

    // 情况三：监视reactive定义的响应式数据
		// 	若watch监视的是reactive定义的响应式数据，则无法正确获得oldValue！！
		// 	若watch监视的是reactive定义的响应式数据，则强制开启了深度监视
    // watch(person,(newValue,oldValue)=>{
    //   console.log('person变化了，',newValue,oldValue);
    // },{immediate:true,deep:false})


    //情况四：监视reactive定义的响应式数据中的某个属性
    // watch(()=>person.firstName,(newValue,oldValue)=>{
    //   console.log('person中的firstName变化了' ,newValue,oldValue);
    // })

    //情况五：监视reactive定义的响应式数据中的某些属性
    // watch([()=>person.firstName,()=>person.lastName],(newValue,oldValue)=>{
    //   console.log('person中的两个变化了' ,newValue,oldValue);
    // })

    //特殊情况
    watch(()=>person.job,(newValue,oldValue)=>{
      console.log('person的job变化了',newValue,oldValue);
    },{deep:true})


   

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