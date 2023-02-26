<template>
  <div class="home">
    Home
    <PostList :posts="posts"/>
    
    
  </div>
</template>

<script>
// @ is an alias to /src

import { ref, computed, watch, watchEffect } from 'vue'
import PostList from '../components/PostList.vue'

export default {
  name: 'HomeView',
  components: { PostList },
  setup() {
    const posts = ref([
      { title: "welcome", body: "hello", id: 1},
      { title: "not welcome", body: "goodbye", id: 2}
    ])

    return { posts }
  }
  
  
}
</script>
