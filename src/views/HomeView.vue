<template>
  <div class="home">
    Home
    <p ref="p">{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <p> {{ ninjaTwo.name }} - {{  ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Updatae ninja2</button>
  </div>
</template>

<script>
// @ is an alias to /src

import { ref, reactive } from 'vue'

export default {
  name: 'HomeView',
  setup() {

    const ninjaOne = ref({ name: 'mario', age: 30 })
    const ninjaTwo = reactive({ name: "luigi", age: 35 })

    const nameOne = ref('mario')
    const nameTwo = reactive('luigi')

    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }

    const updateNinjaTwo = () => {
      ninjaTwo.age = 40
      nameTwo = 'mario'
    }

    return { ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo, nameTwo }
  }
  
  
}
</script>
