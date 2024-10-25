<script setup lang="ts">
import GameHeader from "./components/GameHeader.vue";
import GameFigure from "./components/GameFigure.vue";
import GameWrong from "./components/GameWrong.vue";
import GameWord from "./components/GameWord.vue";
import GamePopup from "./components/GamePopup.vue"
import GameNotofication from "./components/GameNotofication.vue"
import { ref, computed } from 'vue'

const word = ref<string>('игорь');
const letters = ref<string[]>([]);
const correctLetters = computed(() => letters.value.filter(x => word.value.includes(x)))

window.addEventListener('keydown', ({ key }) => {
    if(/[а-яА-ЯеЁ]/.test(key)) {
      letters.value.push(key.toLowerCase())
  }
})
</script>

<template>
  {{ word }}
  {{ letters }}
  {{ correctLetters }}
  <div id="app">
    <GameHeader />
    <div class="game-container">
      <GameFigure />
      <GameWrong />
      <GameWord :word="word" :correct-letters="correctLetters"/>
    </div>
    <!-- Container for final message -->
    <GamePopup v-if="false"/>

    <!-- Notification -->
    <GameNotofication />
    
  </div>
</template>

