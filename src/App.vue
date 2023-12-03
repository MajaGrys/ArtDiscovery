<script setup lang="ts">
import { RouterView } from 'vue-router';
import Navigation from './components/Navigation.vue';

</script>

<template>
	<Navigation />
	<main>
		<Suspense>
			<RouterView />
		</Suspense>
	</main>
</template>

<style lang="css">
*, *::before, *::after {
 	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

html {
	position: relative;
	width: 100vw;
	height: 100vh;
}

section {
	position: absolute;
	top: 58px;
	bottom: 10px;
	left: 10px;
	right: 10px;
	padding: 20px;
	border: solid 1px green;
}

</style>