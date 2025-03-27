<script setup lang="jsx">
import { ref } from 'vue'
import Pagemenu from './pages/PageMenu.vue'
import Pagetimer from './pages/PageTimer.vue'
import Pagequestions from './pages/PageQuestions.vue'
import Pagequestionnaire from './pages/PageQuestionnaire.vue'

var currentPage = ref("Menu")

const pages = {
  "Menu": Pagemenu,
  "Timer": Pagetimer,
  "Questions": Pagequestions,
  "Questionnaire": Pagequestionnaire
}
const changePage = (page) => {
  currentPage.value = page
}
</script>

<template>
  <component :is="pages[currentPage]"/>
  <div id="app">
    <!--Main menu buttons for the Timer and Questionnaire pages.-->
    <button
      v-if="currentPage == 'Menu'"
      @click="changePage('Timer')">Set a Timer
    </button>
    <button 
      v-if="currentPage == 'Menu'"
      @click="changePage('Questionnaire')">Take a Short Questionnaire
    </button>

    <!--Buttons for the questionnaire.-->
    <button 
      v-if="currentPage == 'Questionnaire'"
      @click="changePage('Questions')">Take a Short, Self-Diagnostic Questionnaire!
    </button>
    <button
      v-if="currentPage == 'Questions'"
      @click="changePage('Menu')">Submit</button>

    
    <!--Button to return to the main menu.-->
    <button 
      v-if="currentPage !== 'Menu'"
      @click="changePage('Menu')">Return to Menu
    </button>
  </div>
</template>