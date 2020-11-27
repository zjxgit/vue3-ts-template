<template>
  <div class="home">
    <Demo msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Demo from '@/components/demo/index.vue' // @ is an alias to /src

export default defineComponent({
  name: 'Home',
  components: {
    Demo
  },
  setup() {}
})
</script>
