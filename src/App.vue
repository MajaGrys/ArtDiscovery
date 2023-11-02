<script setup lang="ts">
import { RouterView } from 'vue-router';
import Navigation from './components/Navigation.vue';

</script>

<template>
  <Navigation />
  <RouterView />
</template>

<style lang="css">
*, *::before, *::after {
 	box-sizing: border-box;
	margin: 0;
	padding: 0;
}
</style>