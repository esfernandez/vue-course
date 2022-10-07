
<template>
  <div class="home">
    <h3>{{counterTitle}}</h3>
    <div>
    
      <button @click="decreaseCounter" class="btn">-</button>
      
      <span class="counter">{{counter}}</span>

      <button @click="increaseCounter" class="counter">+</button>
    </div>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input type="text" v-model="counterTitle" />
    </div>
  </div>
</template>

<script setup>
  import {ref} from 'vue'
  
  const counter = ref(10),
        counterTitle = ref('My counter')


  const increaseCounter = () => {
    counter.value++;
  }

  const decreaseCounter = () => {
    counter.value--;
  }
</script>

<!--
<script>
  import {ref} from 'vue'


  export default{
    setup(){
      const counter = ref(10);

      const increaseCounter = () => {
        counter.value++;
      }

      const decreaseCounter = () => {
        counter.value--;
      }

      return {
        counter,
        increaseCounter,
        decreaseCounter
      }
    }
  }
</script>
-->

<!--
<script>
export default{
  data(){
    return {counter: 100}
  },

  methods:{
    increaseCounter(){
      this.counter++;
    },

    decreaseCounter(){
      this.counter--;
    }
  }
}
</script>
-->

<style>
  .home{
    text-align: center;
    padding: 20px;
  }

  .btn, .counter{
    font-size: 40px;
    margin: 10px;
  }

  .edit{
    margin-top: 60px;
  }
</style>