<script setup lang="ts">
import { RouterView } from 'vue-router';
import Navigation from './components/Navigation.vue';

</script>

<template>
  <Navigation />
  <main>
	<Suspense><RouterView /></Suspense>
  </main>
</template>

<style lang="css">
*, *::before, *::after {
 	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

main {
	width: 90vw;
	height: 80vh;
	margin: auto;
	border: 1px black solid;
	padding: 20px;
}

</style>