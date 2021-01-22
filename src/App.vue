<template>
  <AutoComplete serviceUrl="http://localhost:8080/schools/"/>
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

</style>
