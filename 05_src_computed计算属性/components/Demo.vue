<template>
  <h1>一个人的信息</h1>
  <input type="text" v-model="person.firstName">
  <br>
  <input type="text" v-model="person.lastName">
  <span>全名：{{ fullName }}</span>
</template>

<script>
import { reactive, computed } from "vue";
export default {
  name: "App",
  setup() {
    let person = reactive({
      firstName: "张",
      lastName:'三'
    });
    let fullName = computed(()=>{
      return person.firstName + '-' + person.lastName
    })
    return {
        person,
        fullName
    }
  }
};
</script>

<style>

</style>