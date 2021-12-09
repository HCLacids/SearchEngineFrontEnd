<script setup lang="ts">
import { reactive } from 'vue'

defineProps<{ onchange:(str: string) => void }>();

const state = reactive({value: ''});
</script>

<template>
    <div class="container">
        <h2>HCL's Search</h2>
        <input class="input" v-model = "state.value" @input="() => onchange(state.value)" />
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