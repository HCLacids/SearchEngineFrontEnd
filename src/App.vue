<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
// import SearchInput from './components/SearchInput.vue';
import ResultList from './components/ResultList.vue';
import { reactive } from 'vue';

const state = reactive({value: '', result: {list:[]}});

let timer:ReturnType<typeof setTimeout> | null = null;

const handleChange = () => {
    if(timer) {
        clearTimeout(timer);
    }
    timer = setTimeout(()=> {
        fetch('api/search?text=' + state.value, {
            method: 'GET',
            headers : { 
                'Content-Type': 'application/json',
                'Accept': 'application/json',
            }
        }).then((response) => {
            return response.json();
        }).then((res) => {
            state.result = res;
        })
    },1000)
}
</script>

<template>
  <div class="container">
        <h2>HCL's Search</h2>
        <input class="input" v-model = "state.value" @input="handleChange" />
    </div>
  <ResultList :results = "state.result.list" :is = "state.result.list.length > 0? true : false" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.container {
    width: 100%;
    text-align: center;
}

.input {
    width: 300px;
    border: 1px transparent solid;
    box-shadow: 0.5px 1px 0.5px 0.5px darkgray;
    padding: 1em;
    outline: none;
    border-radius: 2em;
}

.input:focus {
    box-shadow: none;
    border: 1px rgb(0, 119, 255) solid;
}
</style>
