<script setup lang="ts">
import { RouterLink } from 'vue-router';
</script>

<template>
    <nav>
        <div>
            ArtDiscovery
        </div>
        <div>
            <RouterLink to="/" class="link">Home</RouterLink>
            <RouterLink to="/discover" class="link">Discover Art</RouterLink>
            <RouterLink to="/about" class="link">About</RouterLink>
        </div>
    </nav>
</template>

<style lang="css">
nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 60px;
    margin: 0 20px;
    
    .link {
        margin: 30px;
        text-decoration: none;

        &:hover {
            color: green;
            transition: 0.3s;
        }
    }
}
</style>