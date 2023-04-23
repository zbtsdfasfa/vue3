<template>
    <div class="app1">
      <h3>我是child组件</h3>
      <p>{{ car.name }}</p>
      <son/>
    </div>
  </template>
  
  <script>
    import Son from './Son.vue'
    import { inject } from 'vue';
  export default {
    name: "Child",
    components:{Son},
    setup(){
        let car = inject('car')
        return {
            car
        }
    }
  };
  </script>
  
  <style>
  .app1{
    background: skyblue;
    padding: 10px;
  }
  </style>