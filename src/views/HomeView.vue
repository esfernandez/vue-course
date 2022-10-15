
<template>
  <div class="home">
    <h3>{{stateForm.title}}:</h3>
    <div>
    
      <button @click="decreaseCounter" class="btn">-</button>
      
      <span class="counter">{{stateForm.counter}}</span>

      <button @click="increaseCounter" class="counter">+</button>
    </div>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input type="text" v-model="stateForm.title" v-focus />
    </div>
  </div>
</template>

<script setup>
  import {ref, reactive, watch, onBeforeUnmount, onUnmounted, onBeforeMount, onMounted} from 'vue'
  import {vFocus} from '@/directives/vFocus'
  // const counter = ref(10),
  //       counterTitle = ref('My counter');

  const stateForm = reactive({
    counter: 5,
    title: 'Mi titulo'
  })

  watch( () => stateForm.counter, (newValue) =>{
    if (newValue === 20) alert("Superaste el valor 20")
  })

  const increaseCounter = () => {
    stateForm.counter++;
  }

  const decreaseCounter = () => {
    stateForm.counter--;
  }

  onBeforeUnmount(() => {
    console.log("Before unmount");
  })
  onUnmounted(() => {
    console.log("Unmounted");
  })
  onBeforeMount(() => {
    console.log("Before mount");
  })
  onMounted(() => {
    console.log("Mount");
  })
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