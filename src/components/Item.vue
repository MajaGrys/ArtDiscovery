<script setup lang="ts">
defineProps<{item}>()
</script>
<template>
    <div class="container">
        <img src="" />
        <div class="name"> {{ item.title }}</div>
        <div class=""> {{ item.category }}</div>
    category, description, price, rating
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