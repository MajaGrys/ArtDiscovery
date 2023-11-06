<script setup lang="ts">
import axios from 'axios';

type ItemType = {
    category: string,
    description: string,
    id: number,
    image: string,
    price: number,
    rating: object,
    title: string
}

const items:Array<Object> = [];

axios.get('https://fakestoreapi.com/products')
.then(function (response) {response.data.forEach(element => {
    items.push(element);
});});

console.log(items)

</script>

<template>
    <div class="container" v-for="item in items">
        <img src={{ item.image }} /> 
        <div class="name"> {{ item.title }}</div>
    {{ item.category }}, {{ item.description }}, {{ item.price }}, rating
    </div>    
</template>

<style lang="css" scoped>
.container {
    margin: 10px;

    .name {
        font-size: x-large;
    }
}
</style>