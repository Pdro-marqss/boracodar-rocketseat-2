<script setup lang="ts">
</script>

<template>
  <section id="products-page">
    <div id="left-side"></div>
    <div id="right-side"></div>
  </section>
</template>

<style scoped>
#products-page {
  height: 100dvh;

  display: grid;
  grid-template-columns: repeat(2, 1fr);
}

#left-side {
  background-color: red;
}
</style>
