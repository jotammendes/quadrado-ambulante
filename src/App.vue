<script setup lang="ts">
  import { RouterView } from 'vue-router';
  import  Header from '@/components/Header.vue';
  import  Footer from '@/components/Footer.vue';
</script>

<template>
  <Header />

  <main>
    <RouterView />
  </main>

  <Footer />
</template>

<style>
  * {
    box-sizing: border-box;
    padding: 0;
    margin: 0;

    max-width: 100vw;
    max-height: 100vh;
  }

  main {
    display: grid;
    grid-template-columns: 1fr;
    justify-content: center;
    align-items: center;

    width: 100vw;
    height: calc(100vh - 119px);
    padding: 1rem;

    background-color: #fafafa;
  }
</style>
