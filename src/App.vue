<script setup lang="ts">
import HomePage from './components/HomePage.vue';

const Checking : boolean = false;


</script>

<template>

<div  v-if="Checking">
    <HomePage />
</div>


</template>

<style >

</style>
