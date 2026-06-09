<script setup>
import { ref } from 'vue'

const emit = defineEmits(['navigate'])

const email = ref('')

function goHome() {
  emit('navigate', 'home')
}

function goSignup() {
  emit('navigate', 'signup-choose')
}
</script>

<template>
  <div class="login-bg">
    <div class="login-card">
      <!-- Logo -->
      <div class="logo-wrap">
        <img src="/image/pp_fc_hl.svg" alt="PayPal" class="logo" @click="goHome" />
      </div>

      <!-- Form -->
      <form class="login-form" @submit.prevent>
        <div class="input-group">
          <input
            id="login-email"
            v-model="email"
            type="email"
            placeholder="電子郵件或手機號碼"
            autocomplete="email"
          />
        </div>

        <a href="#" class="forgot-link">忘記電子郵件？</a>

        <button type="submit" class="btn-next">下一步</button>

        <div class="divider">
          <span>或者</span>
        </div>

        <button type="button" class="btn-signup" @click="goSignup">註冊</button>
      </form>

      <!-- Language -->
      <div class="lang-row">
        <span class="globe">🌐</span>
        <span class="lang-text">中文 ∨</span>
        <span class="lang-sep">|</span>
        <a href="#">English</a>
      </div>
    </div>

    <!-- Bottom Footer -->
    <footer class="login-footer">
      <a href="#">聯絡我們</a>
      <a href="#">隱私權聲明</a>
      <a href="#">法律條款</a>
      <a href="#">全球服務</a>
    </footer>
  </div>
</template>

<style scoped>
.login-bg {
  min-height: 100vh;
  background: #f5f5f5;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.login-card {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 16px rgba(0, 0, 0, 0.12);
  padding: 40px 36px 32px;
  width: 100%;
  max-width: 400px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0;
}

.logo-wrap {
  margin-bottom: 24px;
}

.logo {
  height: 30px;
  cursor: pointer;
}

.login-form {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.input-group {
  margin-bottom: 14px;
}

.input-group input {
  width: 100%;
  padding: 14px 16px;
  border: 1px solid #c4c4c4;
  border-radius: 6px;
  font-size: 15px;
  outline: none;
  transition: border-color 0.2s;
  font-family: inherit;
  color: var(--text-dark);
}

.input-group input:focus {
  border-color: var(--paypal-blue);
  box-shadow: 0 0 0 2px rgba(0, 112, 186, 0.15);
}

.forgot-link {
  font-size: 14px;
  color: var(--paypal-blue);
  font-weight: 600;
  margin-bottom: 20px;
  display: inline-block;
  text-decoration: none;
}

.forgot-link:hover {
  text-decoration: underline;
}

.btn-next {
  width: 100%;
  padding: 14px;
  background: var(--paypal-blue);
  color: #fff;
  border: none;
  border-radius: 999px;
  font-size: 17px;
  font-weight: 700;
  cursor: pointer;
  font-family: inherit;
  transition: background 0.2s;
  margin-bottom: 20px;
}

.btn-next:hover {
  background: var(--paypal-dark);
}

.divider {
  text-align: center;
  color: #9ea3a8;
  font-size: 14px;
  margin-bottom: 20px;
  position: relative;
}

.divider::before,
.divider::after {
  content: '';
  position: absolute;
  top: 50%;
  width: 42%;
  height: 1px;
  background: #d9d9d9;
}

.divider::before { left: 0; }
.divider::after { right: 0; }

.btn-signup {
  width: 100%;
  padding: 13px;
  background: #fff;
  color: var(--text-dark);
  border: 1px solid #c4c4c4;
  border-radius: 999px;
  font-size: 17px;
  font-weight: 700;
  cursor: pointer;
  font-family: inherit;
  transition: background 0.2s, border-color 0.2s;
  margin-bottom: 28px;
}

.btn-signup:hover {
  border-color: var(--paypal-blue);
  color: var(--paypal-blue);
}

.lang-row {
  display: flex;
  align-items: center;
  gap: 6px;
  font-size: 13px;
  color: #6b6f76;
}

.lang-row a {
  color: var(--paypal-blue);
  font-weight: 600;
  text-decoration: none;
}

.lang-row a:hover { text-decoration: underline; }

.lang-sep {
  color: #b0b4b8;
}

.login-footer {
  margin-top: 28px;
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  justify-content: center;
  font-size: 13px;
}

.login-footer a {
  color: #6b6f76;
  text-decoration: none;
}

.login-footer a:hover {
  text-decoration: underline;
  color: var(--paypal-blue);
}
</style>
