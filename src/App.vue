<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import Navigation from './components/Navigation.vue';
import Item from './components/Item.vue';
</script>

<template>
  <Navigation />
  <Item />
  <RouterView />
</template>

<style lang="scss">
</style>