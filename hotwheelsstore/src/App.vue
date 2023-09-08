<script setup>
  import { ref, reactive, onMounted } from 'vue'
  import { db } from './data/hotwheels.js'
  import HotWheel from './components/HotWheel.vue'

  const hotwheels = ref([])

  onMounted(() => {
    hotwheels.value = db;
  })
</script>

<template>
  <header>
    <h1>Hot Wheels Store</h1>
  </header>

  <section>
    <h2>Welcome to our store!</h2>
  </section>

  <main>
    <h2>Our collection</h2>
    <section class="father" v-for="hotwheel in hotwheels">
      <section class="child">
        <div class="hotwheel-pic">
          <img
          v-bind:src="'/img/' + hotwheel.imagen + '.png'"
          v-vind:alt="'image hotwheel ' + hotwheel.nombre"
          >
        </div>
        <div class="hotwheel-data">
          <h3>{{ hotwheel.nombre }}</h3>
          <p>{{ hotwheel.descripcion }}</p>
          <p>${{ hotwheel.precio }}</p>
          <button>Add</button>
        </div>
      </section>
    </section>
  </main>

  <footer>
    <p>Made with 💜 by Sebastián Prieto</p>
  </footer>
</template>

<style scoped>
</style>
