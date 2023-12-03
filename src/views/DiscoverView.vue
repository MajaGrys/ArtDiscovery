<script setup lang="ts">
import axios from 'axios';
import { computed } from 'vue';

const res = await axios.get('https://api.artic.edu/api/v1/artworks/search?query[term][is_public_domain]=true&limit=5&fields=id,title,image_id, artist_title')
const data = res.data.data

const filteredData = computed(() => {
    return data.filter(item => item.image_id !== null)
})

</script>

<template>
<section class="gallery">
<div v-for="item in filteredData" :key="item.image_id">
    <div class="item-box">
        <img :src="'https://www.artic.edu/iiif/2/' + item.image_id + '/full/843,/0/default.jpg'" />
        <div class="description">
            {{ item.title }} by {{ item.artist_title === null ? 'Unknown' : item.artist_title }}
        </div>
    </div>
</div>
</section>
</template>

<style lang="css" scoped>
.gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    overflow: auto;
}

.item-box {
    width: 300px;
    position: relative;
}

img {
    width: inherit;
    border: 1px solid black;
}

.item-box:hover img {
    opacity: 50%;
    transition: 0.3s;
}

.description {
    height: auto;
    opacity: 0;
    position: absolute;
    bottom: 10px;
    left: 10px;
    margin: 10px;
}

.item-box:hover .description {
    opacity: 100%;
    transition: 0.3s;
}
</style>