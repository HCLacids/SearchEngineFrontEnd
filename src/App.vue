<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import SearchInput from './components/SearchInput.vue';
import ResultList from './components/ResultList.vue';

const res = [{text:"1222",link:"#", description:"1223"},
  {text:"1222",link:"#", description:"1223"},
  {text:"1222",link:"#", description:"1223"},
  {text:"1222",link:"#", description:"1223"},
  {text:"1222",link:"#", description:"1223"},
  {text:"1222",link:"#", description:"1223"},
  {text:"1222",link:"#", description:"1223"}]
</script>

<template>
  <SearchInput />
  <ResultList :results="res" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
