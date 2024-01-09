<script setup lang="ts">
import { ref, reactive, computed } from 'vue';

let product = reactive({
  image: true,
})

const icon = ref('/icon360.svg');

function changeState() {
  product.image = !product.image;
  icon.value = icon.value === '/icon360.svg' ? '/iconClose.svg' : '/icon360.svg';
}

const productImage = computed(() => {
  return product.image ? '/sofa.svg' : '/sofa.gif'
})
</script>

<template>
  <section id="products-page">
    <div id="left-side">
      <div class="image">
        <img :src="productImage" alt="imagem de um sofá rosa">
        <img :src="icon" alt="imagem de um icone escrito 360" @click="changeState">
      </div>
    </div>
    <div id="right-side">
      <div class="content">
        <p>CÓDIGO: 42404</p>
        <h1>Sofá Margot II - Rosé</h1>
        <p>R$ 4.000</p>
        <button>ADICIONAR A CESTA</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
#products-page {
  background-color: #D9CDF7;

  height: 100dvh;

  display: grid;
  grid-template-columns: repeat(2, 1fr);

  font-family: 'Lato', sans-serif;
}

#left-side {
  display: flex;
  place-items: center;
  justify-content: flex-end;
}

#left-side .image {
  position: relative;
}

#left-side .image img:first-child {
  width: 449px;
}

#left-side .image img:last-child {
  position: absolute;
  right: 60px;
  top: 0;
  cursor: pointer;
}

#right-side {
  display: flex;
  place-items: center;
}

#right-side .content p {
  color: #271a45;
}

#right-side .content p:first-child {
  font-size: 14px;
  font-weight: 300;
}

#right-side .content h1 {
  margin: 12px 0;

  font-family: 'Crimson Pro', serif;
  font-size: 32px;
  font-weight: 600;
}

#right-side .content p:nth-of-type(2) {
  font-size: 18px;
  font-weight: 400;
}

#right-side .content button {
  background-color: transparent;

  border: 0.5px solid #271A45;
  border-radius: 999px;

  margin-top: 20px;
  padding: 8px 16px;

  cursor: pointer;
}
</style>
