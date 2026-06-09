<script setup>
import { ref } from 'vue'
import HomeLanding from './components/HomeLanding.vue'
import LoginPage from './components/LoginPage.vue'
import SignupChoose from './components/SignupChoose.vue'
import SignupPersonal from './components/SignupPersonal.vue'
import SignupBusiness from './components/SignupBusiness.vue'

const currentPage = ref('home')

function navigate(page) {
  currentPage.value = page
}
</script>

<template>
  <div class="app-container">
    <component :is="
      currentPage === 'home' ? HomeLanding :
      currentPage === 'login' ? LoginPage :
      currentPage === 'signup-choose' ? SignupChoose :
      currentPage === 'signup-personal' ? SignupPersonal :
      currentPage === 'signup-business' ? SignupBusiness : null
    " @navigate="navigate" />
  </div>
</template>

<style scoped>
.app-container {
  width: 100%;
  overflow-x: hidden;
  display: flex;
  flex-direction: column;
}
</style>

