<template>
<Header></Header>
<div class="container mb-10">
  <router-view/>
</div>
</template>
<script>
import Header from './components/Header.vue'

 export default {
  components: {
    Header 
  }
 }
</script>
