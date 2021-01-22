<template>
  <AutoComplete 
  placeholder="School name here..."
  serviceUrl="http://localhost:8080/schools/"/>
</template>

<script>
import AutoComplete from './components/AutoComplete.vue'

export default {
  name: 'App',
  components: {
    AutoComplete
  }
}
</script>

<style>
#app {
    display: flex;
    justify-content: center;
    align-items: center;
    height: calc(100vh - 2em);  
}
</style>
