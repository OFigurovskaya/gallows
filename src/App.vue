<script setup lang="ts">
import GameHeader from "./components/GameHeader.vue";
import GameFigure from "./components/GameFigure.vue";
import GameWrong from "./components/GameWrong.vue";
import GameWord from "./components/GameWord.vue";
import GamePopup from "./components/GamePopup.vue"
import GameNotofication from "./components/GameNotofication.vue"
import { ref } from 'vue'

const word = ref('Василий');
</script>

<template>
  <div id="app">
    <GameHeader />
    <div class="game-container">
      <GameFigure />
      <GameWrong />
      <GameWord :word="word"/>
    </div>
    <!-- Container for final message -->
    <GamePopup v-if="false"/>

    <!-- Notification -->
    <GameNotofication />
    
  </div>
</template>

