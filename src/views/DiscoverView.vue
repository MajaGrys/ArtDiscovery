<script setup lang="ts">
import axios from 'axios';
import { computed } from 'vue';

const res = await axios.get('https://api.artic.edu/api/v1/artworks/search?query[term][is_public_domain]=true&limit=20&fields=id,title,image_id, artist_title')
// https://api.artic.edu/api/v1/artworks/75644

const data = res.data.data

const filteredData = computed(() => {
    return data.filter(item => item.image_id !== null)
})
console.log(data)
</script>

<template>
<div class="gallery">
<div v-for="item in filteredData" :key="item.image_id">
    <div class="item-box">
        <img :src="'https://www.artic.edu/iiif/2/' + item.image_id + '/full/843,/0/default.jpg'" />
        <div class="description">
            {{ item.title }} by {{ item.artist_title === null ? 'Unknown' : item.artist_title }}
        </div>
    </div>
    <!--   -->
</div></div>
</template>

<style lang="css" scoped>
.gallery {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    max-height: 75vh;
    overflow: auto;
}

.item-box {
    width: 250px;
}

img {
    width: inherit;
    border: 6px double black;

    &:hover {
        opacity: 50%;
    }
}

.description {
    position: relative;
    margin: 10px;
    width: 180px;
    cursor: default;

}
</style>