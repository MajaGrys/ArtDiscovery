<script setup lang="ts">
import Item from '@/components/Item.vue';

type ItemType = {
    category: string,
    description: string,
    id: number,
    image: string,
    price: number,
    rating: object,
    title: string
}

const items:[] = [];

const getItems = () => {
    fetch('https://fakestoreapi.com/products')
            .then(res => res.json())
            .then(json => json.map((e:ItemType) => items.push(e)) )
}

getItems();
console.log(items)

</script>

<template>
    <div v-for="item in items"><Item :item="item" /></div>
    
</template>

<style>
</style>