<script setup lang="ts">
  interface Props {
    col: number;
    row: number;
  }

  const props = defineProps<Props>();
</script>

<template>
  <div :class="'square' + ' column-' + props.col + ' row-' + props.row">
  </div>
</template>

<style scoped>
  .square {
    display: block;
    width: calc(100% - 4px);
    height: calc(100% - 4px);

    margin: auto;

    background-color: red;
    border: 2px solid black;
  }

  .column-1 {
    grid-column: 1;
  }
  .column-2 {
    grid-column: 2;
  }
  .column-3 {
    grid-column: 3;
  }
  .column-4 {
    grid-column: 4;
  }
  .column-5 {
    grid-column: 5;
  }
  .column-6 {
    grid-column: 6;
  }
  .column-7 {
    grid-column: 7;
  }
  .column-8 {
    grid-column: 8;
  }

  .row-1 {
    grid-row: 1;
  }
  .row-2 {
    grid-row: 2;
  }
  .row-3 {
    grid-row: 3;
  }
  .row-4 {
    grid-row: 4;
  }
  .row-5 {
    grid-row: 5;
  }
  .row-6 {
    grid-row: 6;
  }
  .row-7 {
    grid-row: 7;
  }
  .row-8 {
    grid-row: 8;
  }
</style>
