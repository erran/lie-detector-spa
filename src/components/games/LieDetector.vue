<script setup>
import { ref } from 'vue'
import beep from '../../sounds/beep'

const results = ref();

function detectLie() {
  const n = Math.floor(Math.random() * 100);
  if (n % 2 === 0) {
    beep.beep();
    results.value = "truth";
  } else {
    beep.beepBeepBeep();
    results.value = "lie";
  }
}
</script>

<template>
  <main>
    <div>
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
    </div>
  </main>
</template>

<style scoped>
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
