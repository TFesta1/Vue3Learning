<template>
  <div class="home">
    Home
    <input type="text" v-model="search">
    <p>searchterm: {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      {{ name }}
    </div>

    <button @click="handleClick">Stop watching</button>
    
  </div>
</template>

<script>
// @ is an alias to /src

import { ref, computed, watch, watchEffect } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'yoshi', 'koopa', 'bowser'])


    // Whenever search changes
    const stopWatch = watch(search, () => {
      console.log('watched')
    })


    // Runs initially, and watches any dependencies inside of it (search.value)
    const stopEffect = watchEffect(() => {
      console.log("watchEffect", search.value)
    })
    
    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const handleClick = () => {
      // Stops it from watching
      stopWatch()
      stopEffect()
    }

    return { matchingNames, search, handleClick }
  }
  
  
}
</script>
