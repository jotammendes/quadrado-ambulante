<script setup lang="ts">
  import { onMounted, reactive } from 'vue';
  import Square from '@/components/Square.vue';

  interface coordinates {
    col: number;
    row: number;
  }

  const state = reactive<coordinates>({
    col: 1,
    row: 1,
  });

  const handleClick = (event: KeyboardEvent) => {
    if(event.key === 'ArrowUp' && state.row > 1) state.row--;
    if(event.key === 'ArrowLeft' && state.col > 1) state.col--;
    if(event.key === 'ArrowDown' && state.row < 8) state.row++;
    if(event.key === 'ArrowRight' && state.col < 8) state.col++;
  };

  onMounted(() => {
    document.addEventListener('keyup', handleClick);
  });
</script>

<template>
  <div class="scenery">
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="1" :isActive="state.col === currentCol && state.row === 1" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="2" :isActive="state.col === currentCol && state.row === 2" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="3" :isActive="state.col === currentCol && state.row === 3" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="4" :isActive="state.col === currentCol && state.row === 4" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="5" :isActive="state.col === currentCol && state.row === 5" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="6" :isActive="state.col === currentCol && state.row === 6" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="7" :isActive="state.col === currentCol && state.row === 7" />
    <Square v-for="currentCol in [1, 2, 3, 4, 5, 6, 7, 8]" :col="currentCol" :row="8" :isActive="state.col === currentCol && state.row === 8" />
  </div>
</template>

<style scoped>
  .scenery {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-template-rows: repeat(8, 1fr);
    gap: 2px;
    justify-content: center;
    align-items: center;

    width: 100%;
    height: 100%;

    background-color: #0b1444;
    border: 5px solid black;
    box-shadow: 0 0 -5px 10px rgba(0, 0, 0, 0.1);
  }
</style>
