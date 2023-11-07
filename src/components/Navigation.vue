<script setup lang="ts">
import { RouterLink } from 'vue-router';
</script>

<template>
    <nav>
        <RouterLink to="/" class="link">Home</RouterLink>
        <RouterLink to="/discover" class="link">Discover Art</RouterLink>
        <RouterLink to="/about" class="link">About</RouterLink>
        <!-- <form>
            <input type="text" name="item" placeholder="Search for items" />
            <button type="submit">Search</button>
        </form> -->
    </nav>
</template>

<style lang="css">
nav {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    padding: 20px;
    
    .link {
        margin: 20px;
        color: black;
        text-decoration: none;

        &:hover {
            color: red;
        }
    }
}

input, button {
    padding: 10px;
    margin: 5px;
    max-width: 150px;
}

button {
    cursor: pointer;
}
</style>