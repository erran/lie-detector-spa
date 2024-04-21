<script setup>
import LieDetector from './components/games/LieDetector.vue'
</script>

<template>
  <header>
    <div class="content">
      <h1>Kai's Gameroom</h1>
    </div>
  </header>

  <main>
    <div class="content">
      <LieDetector/>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

main .content .h1 {
  text-align: center;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .content {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
