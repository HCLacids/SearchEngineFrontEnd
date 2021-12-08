<script setup lang="ts">

defineProps<{ results: {text: string, link: string, description: string}[] }>();

</script>

<template>
    <div class = "containerLi">
        <div v-for = "li in results" class = "resultLiBox">
            <div class = "title"><a :href="li.link" target = "_blank">{{li.text}}</a></div>
            <div class = "description">{{li.description}}</div>
            <div class = "link">{{li.link}}</div>
        </div>
    </div>
</template>

<style>
a {
    text-decoration-color: darkcyan;
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
    font-size: 16px;
}

.link {
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
</style>