<template>
  <div class="home">
    Home
    <p ref="p">name {{ name }} age {{ age }}</p>
    <button @click="handleClick">click</button>
    <button @click="age++">Add1 to age</button>
    <input type="text" v-model="name"> <!-- v-model implements a two-way binding-->
  </div>
</template>

<script>
// @ is an alias to /src

import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup() {

    const name = ref('mario') //ref's are reactive values
    const age = ref(30)
    
    const handleClick = () => {
      name.value = 'luigi' //makes it reactive
    }

    return { name, age, handleClick }
  },
  data() {
    return {
      age: 40
    }
  }
  
  
}
</script>
