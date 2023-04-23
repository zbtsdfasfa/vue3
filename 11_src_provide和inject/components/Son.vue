<template>
    <div class="app2">
      <h3>我是son组件</h3>
      <p>{{ car.name }}----{{ car.price }}</p>
    </div>
  </template>
  
  <script>
    import { inject } from 'vue';
  export default {
    name: "Son",
    setup(){
        let car = inject('car')
        return{
            car
        }
    }
  };
  </script>
  
  <style>
  .app2{
    background: orange;
    padding: 10px;
  }
  </style>