<script setup lang="ts">

defineProps<{ results: {text: string, link: string, description: string}[], is: boolean }>();

</script>

<template>
    <div class = "containerLi" v-if="is">
        <div v-for = "li in results" class = "resultLiBox">
            <div class = "title"><a :href="li.link" target = "_blank">{{li.text}}</a></div>
            <div class = "description">{{li.description}}</div>
            <div class = "link">{{li.link}}</div>
        </div>
    </div>
    <div v-else class = "noneRes">
        No result
    </div>
</template>

<style>
a {
    color: black;
    text-decoration: none;
}

a:hover {
    color: blue;
    text-decoration: underline;
    text-decoration-color: blue;
}
.resultLiBox {
    width: 10em;
    height: 10em;
    margin: 20px;
    padding: 10px;
    box-shadow: 1px 1px 1px 1px darkgray;
    border-radius: 0.5em;
    flex: 1;
    transition: 0.5s ease-in-out;
}
.resultLiBox:hover{
    flex: 1.5;
}
.title {
    margin: 5px 0;
    font-size: 22px;
}
.description {
    margin: 5px 0;
    height: 60px;
    font-size: 16px;
    overflow: hidden;
}

.link {
    width: 100%;
    overflow: hidden;
    color: darkgray;
}

.containerLi {
    padding: 10px;
    width: 80%;
    height: 670px;
    margin: 0 auto;
    overflow: auto;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}

.noneRes {
    width: 80%;
    text-align: center;
    margin: 20px auto;
}
.containerLi::-webkit-scrollbar {
    width: 4px;
    height: 4px;
}
.containerLi::-webkit-scrollbar-track {
    background: #f6f6f6;
    border-radius: 2px;
}
.containerLi::-webkit-scrollbar-thumb {
    background: #aaa;
    border-radius: 2px;
}
.containerLi::-webkit-scrollbar-thumb:hover {
    background: #747474;
}
.containerLi::-webkit-scrollbar-corner {
    background: #f6f6f6;
}
</style>