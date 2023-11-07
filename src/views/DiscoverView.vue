<script setup lang="ts">
import axios from 'axios';
import { computed } from 'vue';

const res = await axios.get('https://api.artic.edu/api/v1/artworks?limit=100&fields=id,title,image_id')
const data = res.data.data

const filteredData = computed(() => {
    return data.filter(item => item.image_id !== null)
})
console.log(data)
</script>

<template>
Discover
<div class="gallery">
<div v-for="item in filteredData" :key="item.image_id">
    <img :src="'https://www.artic.edu/iiif/2/' + item.image_id + '/full/843,/0/default.jpg'" />
    
    <!-- {{ item.title }} by {{ item.artist_title === null ? 'Unknown' : item.artist_title }} -->
</div></div>
</template>

<style lang="css" scoped>
.gallery {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
}
img {
    width: 200px;
    border: 6px double black;
}
</style>