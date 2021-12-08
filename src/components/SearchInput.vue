<script setup lang="ts">
import { reactive } from 'vue'

const state = reactive({value: ''});

let timer:ReturnType<typeof setTimeout> | null = null;

const handleChange = () => {
    if(timer) {
        clearTimeout(timer);
    }
    timer = setTimeout(()=> {
        console.log(state.value);
    },1000)
}
</script>

<template>
    <div class="container">
        <h2>HCL's Search</h2>
        <input class="input" v-model = "state.value" @input="handleChange" />
        {{state.value}}
    </div>
</template>

<style>
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