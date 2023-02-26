<template>
  <div class="home">
    Home
    <p ref="p">name {{ name }} age {{ age }}</p>
    <button @click="handleClick">click</button>
  </div>
</template>

<script>
// @ is an alias to /src

import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    console.log("setup")

    let name = 'mario'
    let age = 30

    const p = ref(null)

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test') //normal js property classList
      p.value.textContent = 'hello, ninjas'
    }

    return { name, age, handleClick, p }
  },
  data() {
    return {
      age: 40
    }
  }
  
  
}
</script>
