<script setup>
import { ref, computed } from 'vue'

const emit = defineEmits(['navigate'])

const lastName   = ref('')
const middleName = ref('')
const firstName  = ref('')
const country    = ref('TW')
const email      = ref('')
const password   = ref('')
const phoneCode  = ref('+886')
const phone      = ref('')

// Password validation checklist
const pwLen     = computed(() => password.value.length >= 8)
const pwCase    = computed(() => /[a-z]/.test(password.value) && /[A-Z]/.test(password.value))
const pwNumSym  = computed(() => /[0-9!@#$%^&*]/.test(password.value))

function goBack()  { emit('navigate', 'signup-choose') }
function goHome()  { emit('navigate', 'home') }
function goLogin() { emit('navigate', 'login') }
</script>

<template>
  <div class="sb-page">
    <!-- Header -->
    <header class="sb-header">
      <img src="/image/pp_fc_hl.svg" alt="PayPal" class="logo" @click="goHome" />
      <button class="btn-login-outline" @click="goLogin">登入</button>
    </header>

    <!-- Form -->
    <main class="sb-main">
      <h1>建立商業帳戶</h1>

      <form class="sb-form" @submit.prevent>
        <!-- Last Name -->
        <div class="field">
          <input id="lastName" v-model="lastName" type="text" placeholder="姓氏" />
          <span class="helper">minimalAccount.lastName.helperText</span>
        </div>

        <!-- Middle Name -->
        <div class="field">
          <input id="middleName" v-model="middleName" type="text" placeholder="中間名" />
        </div>

        <!-- First Name -->
        <div class="field">
          <input id="firstName" v-model="firstName" type="text" placeholder="名字 *" />
        </div>

        <!-- Country -->
        <div class="field">
          <select id="country" v-model="country">
            <option value="TW">台灣</option>
            <option value="US">美國</option>
            <option value="JP">日本</option>
            <option value="HK">香港</option>
          </select>
          <span class="helper">我們會依你所在國家/地區，提供特定地點。請確認你輸入的資料與公司所在地一致。</span>
        </div>

        <!-- Email -->
        <div class="field">
          <input id="sb-email" v-model="email" type="email" placeholder="電子郵件" autocomplete="email" />
        </div>

        <!-- Password -->
        <div class="field">
          <input id="sb-password" v-model="password" type="password" placeholder="密碼" autocomplete="new-password" />
          <!-- Checklist -->
          <ul class="pw-checklist">
            <li :class="{ done: pwLen }">
              <span class="dot">○</span> 輸入至少 8 個字元。
            </li>
            <li :class="{ done: pwCase }">
              <span class="dot">○</span> 使用大小寫字母。
            </li>
            <li :class="{ done: pwNumSym }">
              <span class="dot">○</span> 輸入至少 1 個數字（1 個符號（例如 !@#$%）。
            </li>
          </ul>
        </div>

        <!-- Phone -->
        <div class="field phone-row">
          <select id="phoneCode" v-model="phoneCode" class="phone-code">
            <option value="+886">🌐 +886</option>
            <option value="+1">🌐 +1</option>
            <option value="+81">🌐 +81</option>
            <option value="+852">🌐 +852</option>
          </select>
          <input id="phone" v-model="phone" type="tel" placeholder="電話號碼" class="phone-input" />
        </div>
        <span class="helper">minimalAccount.phoneNoNumber.helperText</span>

        <p class="agree-text">
          按繼續代表同意遵守
          <a href="#">用戶協定</a>
          和
          <a href="#">隱私權聲明</a>。
        </p>

        <button type="submit" class="btn-submit">同意並建立帳戶</button>

        <p class="login-link">
          已有帳戶？ <a href="#" @click.prevent="goLogin">登入</a>
        </p>
      </form>
    </main>

    <!-- Footer -->
    <footer class="sb-footer">
      <div class="footer-left">
        <a href="#">Help</a>
        <a href="#">Contact</a>
        <a href="#">Sitemap</a>
        <a href="#">Fees</a>
        <a href="#">Security</a>
        <a href="#">About</a>
        <a href="#">Developers</a>
        <a href="#">Partners</a>
      </div>
      <div class="footer-right">
        <span>Privacy</span>
        <span>Legal</span>
        <span>Policy updates</span>
        <span>English</span>
      </div>
      <div class="copyright-row">
        Copyright © 1999-2026 PayPal. All rights reserved.
      </div>
    </footer>
  </div>
</template>

<style scoped>
.sb-page {
  min-height: 100vh;
  background: #f5f5f5;
  display: flex;
  flex-direction: column;
}

/* Header */
.sb-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 40px;
  background: #f5f5f5;
}

.logo {
  height: 28px;
  cursor: pointer;
}

.btn-login-outline {
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

.btn-login-outline:hover {
  background: rgba(0, 112, 186, 0.06);
}

/* Main */
.sb-main {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 32px 20px 40px;
}

.sb-main h1 {
  font-size: clamp(22px, 3vw, 30px);
  font-weight: 700;
  color: var(--text-dark);
  margin-bottom: 28px;
  text-align: center;
}

.sb-form {
  width: 100%;
  max-width: 400px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.field {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.field input,
.field select {
  width: 100%;
  padding: 13px 14px;
  border: 1px solid #c4c4c4;
  border-radius: 6px;
  font-size: 15px;
  font-family: inherit;
  background: #fff;
  color: var(--text-dark);
  outline: none;
  transition: border-color 0.2s;
  appearance: auto;
}

.field input:focus,
.field select:focus {
  border-color: var(--paypal-blue);
  box-shadow: 0 0 0 2px rgba(0, 112, 186, 0.15);
}

.helper {
  font-size: 12px;
  color: var(--text-light);
  padding-left: 2px;
}

/* Phone row */
.phone-row {
  flex-direction: row;
  gap: 8px;
}

.phone-code {
  width: 120px;
  flex-shrink: 0;
}

.phone-input {
  flex: 1;
}

/* Password checklist */
.pw-checklist {
  list-style: none;
  padding: 6px 0 0 2px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.pw-checklist li {
  font-size: 13px;
  color: var(--text-light);
  display: flex;
  align-items: flex-start;
  gap: 6px;
  transition: color 0.2s;
}

.pw-checklist li.done {
  color: #2e7d32;
}

.pw-checklist li.done .dot::before {
  content: '●';
}

.dot::before {
  content: '○';
}

.dot {
  display: none; /* using ::before pseudo-element */
}

/* Agree text */
.agree-text {
  font-size: 13px;
  color: var(--text-light);
  line-height: 1.6;
}

.agree-text a {
  color: var(--paypal-blue);
  text-decoration: none;
}

.agree-text a:hover { text-decoration: underline; }

/* Submit button */
.btn-submit {
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
  margin-top: 4px;
}

.btn-submit:hover {
  background: #333;
}

.login-link {
  text-align: center;
  font-size: 14px;
  color: var(--text-light);
}

.login-link a {
  color: var(--paypal-blue);
  font-weight: 600;
  text-decoration: none;
}

.login-link a:hover { text-decoration: underline; }

/* Footer */
.sb-footer {
  background: #f5f5f5;
  border-top: 1px solid #dde0e3;
  padding: 16px 40px 12px;
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.footer-left,
.footer-right {
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
  font-size: 12px;
}

.footer-left {
  justify-content: flex-start;
}

.footer-right {
  justify-content: flex-end;
  color: var(--text-light);
}

.footer-left a {
  color: var(--text-light);
  text-decoration: none;
}

.footer-left a:hover {
  color: var(--paypal-blue);
  text-decoration: underline;
}

.copyright-row {
  font-size: 11px;
  color: #9ea3a8;
  text-align: left;
  margin-top: 4px;
}
</style>
