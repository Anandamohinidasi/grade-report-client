<template>
<div class="input-container">
<input class="search"
       type="text" 
       v-model="searchQuery" 
       :placeholder="placeholder"
       @keypress="search">
<ul class="suggestion-list" v-if="searchQuery">
  <li v-for="suggestion in suggestionList" 
      :key="suggestion._id"
      @click="select(suggestion)">
    {{suggestion.name}}
  </li>
</ul>
</div>
</template>

<script>
export default {
  name: 'AutoComplete',
  props: {
    serviceUrl: String,
    placeholder: String
  },
  data() {
    return {
      searchQuery: '',
      suggestionList: []
    }
  },
  methods: {
    select(suggestion) {
      this.searchQuery = suggestion.name;
    },
    search() {
      if(this.searchQuery === '') return;
      fetch(this.serviceUrl + this.searchQuery)
      .then(response => response.json())
      .then(parsedRes => this.suggestionList = parsedRes)
      .catch(error => console.error(error))
    }
  }

}
</script>

<style scoped lang="scss">
.input-container {
  position: relative;
  .search {
      border: 1px solid #d4dde5;
      border-radius: 6px;
      height: 3em;
      width: 80vw;
      max-width: 25em;
      outline: none;
      font-size: 1em;
      transition: all 0.20s ease-in-out;
      &:focus {
        box-shadow: 0 0 5px rgba(81, 203, 238, 1);
      }
  }
  ul.suggestion-list {
    border: 1px solid #d4dde5;
    border-radius: 0 0 6px 6px;
    padding: 0;
    cursor: pointer;
    width: 100%;
    position: absolute;
    li {
      list-style: none;
      padding: .6em;
      &:hover { 
         background:#d4dde5;
      }
    }
}
}
</style>
