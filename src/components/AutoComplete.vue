<template>
<div class="input-container">
<input class="search" type="text">
<ul class="suggestion-list">
</ul>
</div>
</template>

<script>
export default {
  name: 'http://localhost:8080/schools/ONTA',
  props: {
    serviceUrl: String
  }

}
</script>

<style scoped lang="scss">
  .search {
      border: 1px solid #e3e8ec;
      border-radius: 6px;
      height: 2em;
      width: 80%;
      max-width: 25em;
      outline: none;
      transition: all 0.20s ease-in-out;
      &:focus {
        box-shadow: 0 0 5px rgba(81, 203, 238, 1);
      }
  }
</style>
