<script setup>
import { ref } from 'vue'

const emit = defineEmits(['navigate'])

const email = ref('')

function goBack() { emit('navigate', 'signup-choose') }
function goLogin() { emit('navigate', 'login') }
function goHome() { emit('navigate', 'home') }
</script>

<template>
  <div class="signup-personal-page">
    <!-- Header -->
    <header class="sp-header">
      <div class="sp-header-left">
        <span class="globe-btn">🌐 ∨</span>
      </div>
      <img src="/image/pp_fc_hl.svg" alt="PayPal" class="logo" @click="goHome" />
      <div class="sp-header-right">
        <button class="btn-login" @click="goLogin">登入</button>
      </div>
    </header>

    <!-- Main -->
    <main class="sp-main">
      <h1>註冊PayPal</h1>
      <form class="sp-form" @submit.prevent>
        <input
          id="sp-email"
          v-model="email"
          type="email"
          placeholder="你的電子郵件"
          autocomplete="email"
        />
        <button type="submit" class="btn-next">下一步</button>
      </form>
    </main>

    <!-- Footer -->
    <footer class="sp-footer">
      <span>©2026 PayPal</span>
      <a href="#">隱私權聲明</a>
      <a href="#">法律條款</a>
      <a href="#">聯絡我們</a>
      <a href="#">意見調查</a>
      <span>中文 ∨</span>
    </footer>
  </div>
</template>

<style scoped>
.signup-personal-page {
  min-height: 100vh;
  background: #f5f5f5;
  display: flex;
  flex-direction: column;
}

/* Header */
.sp-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 14px 28px;
  background: #f5f5f5;
}

.logo {
  height: 28px;
  cursor: pointer;
}

.globe-btn {
  font-size: 14px;
  color: var(--text-light);
  cursor: pointer;
}

.btn-login {
  padding: 8px 22px;
  border: 1.5px solid var(--paypal-blue);
  border-radius: 999px;
  background: #fff;
  color: var(--paypal-blue);
  font-size: 14px;
  font-weight: 700;
  cursor: pointer;
  font-family: inherit;
  transition: all 0.2s;
}

.btn-login:hover {
  background: rgba(0, 112, 186, 0.06);
}

/* Main */
.sp-main {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 40px 20px;
}

.sp-main h1 {
  font-size: clamp(24px, 3vw, 36px);
  font-weight: 700;
  color: var(--text-dark);
  margin-bottom: 28px;
  text-align: center;
}

.sp-form {
  width: 100%;
  max-width: 360px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.sp-form input {
  width: 100%;
  padding: 14px 16px;
  border: 1px solid #c4c4c4;
  border-radius: 6px;
  font-size: 15px;
  font-family: inherit;
  outline: none;
  transition: border-color 0.2s;
  background: #fff;
}

.sp-form input:focus {
  border-color: var(--paypal-blue);
  box-shadow: 0 0 0 2px rgba(0, 112, 186, 0.15);
}

.btn-next {
  width: 100%;
  padding: 14px;
  background: #111;
  color: #fff;
  border: none;
  border-radius: 999px;
  font-size: 17px;
  font-weight: 700;
  cursor: pointer;
  font-family: inherit;
  transition: background 0.2s;
}

.btn-next:hover {
  background: #333;
}

/* Footer */
.sp-footer {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 14px;
  padding: 16px 20px 24px;
  font-size: 12px;
  color: var(--text-light);
}

.sp-footer a {
  color: var(--text-light);
  text-decoration: none;
}

.sp-footer a:hover {
  color: var(--paypal-blue);
  text-decoration: underline;
}
</style>
