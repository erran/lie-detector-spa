<script setup>
import { ref } from 'vue'
import { beep, beepBeepBeep } from './sounds/beep'

const results = ref();

function detectLie() {
  const n = Math.floor(Math.random() * 100);
  if (n % 2 === 0) {
    beep();
    results.value = "truth";
  } else {
    beepBeepBeep();
    results.value = "lie";
  }
}
</script>

<template>
  <main>
    <div>
      <h4 style="text-align: center">
        <button :class="{
          'btn-detector': true,
          truth: results === 'truth',
          lie: results === 'lie',
        }" @click="detectLie">
          <span style="text-align: center" v-if="results">
            That was a {{ results }}.

            Click to try again.
          </span>
          <span style="text-align: center" v-else>
            Click the button to detect lies.
          </span>
        </button>
      </h4>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.btn-detector {
  background-color: red;
  color: white;
  font-size: 24px;
  min-width: 400px;
  min-height: 500px;
}

.lie {
  background-color: red;
}

.truth {
  background-color: green;
}
</style>
