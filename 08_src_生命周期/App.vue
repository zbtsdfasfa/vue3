<template>
  <Demo v-if="isShow"/>
  <button @click="isShow = !isShow">显示|隐藏</button>
</template>

<script>
import {ref} from 'vue'
import Demo from './components/Demo.vue'
export default {
  name: "App",
  components:{Demo},
  setup(){
    let isShow = ref(true)
    return {
      isShow
    }
  }
  
};
</script>

<style>

</style>
