<script setup>
const emit = defineEmits(['navigate'])

function goLogin() { emit('navigate', 'login') }
function goHome() { emit('navigate', 'home') }
function choosePersonal() { emit('navigate', 'signup-personal') }
function chooseBusiness() { emit('navigate', 'signup-business') }
</script>

<template>
  <div class="choose-page">
    <!-- Header -->
    <header class="choose-header">
      <img src="/image/pp_fc_hl.svg" alt="PayPal" class="logo" @click="goHome" />
      <button class="btn-login" @click="goLogin">登入</button>
    </header>

    <!-- Main -->
    <main class="choose-main">
      <h1>免費註冊 PayPal 帳戶</h1>
      <p class="subtitle">請先選擇你的帳戶種類</p>

      <div class="cards">
        <!-- Personal -->
        <div class="account-card">
          <h2>個人帳戶</h2>
          <button class="btn-register" @click="choosePersonal">立即註冊</button>
          <ul>
            <li>向全球數百萬商家線上付款。</li>
            <li>符合資格的交易享有「買家購物安全保障」。</li>
          </ul>
        </div>

        <!-- Business -->
        <div class="account-card">
          <h2>商業帳戶</h2>
          <button class="btn-register" @click="chooseBusiness">立即註冊</button>
          <ul>
            <li>適用於公司或規模經營。</li>
            <li>跨境付款和收款。</li>
            <li>設定定費或月費。</li>
            <li>符合資格的交易享有「賣家交易安全保障」。</li>
          </ul>
        </div>
      </div>
    </main>

    <!-- Footer -->
    <footer class="choose-footer">
      <nav class="footer-links">
        <a href="#">查詢中心</a>
        <a href="#">聯絡我們</a>
        <a href="#">費用</a>
        <a href="#">交易安全</a>
        <a href="#">全球購物優惠</a>
      </nav>
      <div class="footer-bottom">
        <nav class="footer-links">
          <a href="#">關於 PayPal</a>
          <a href="#">新聞中心</a>
          <a href="#">工作情報</a>
          <a href="#">開發人員</a>
          <a href="#">合作夥伴</a>
        </nav>
        <div class="lang-right">
          <span>English</span>
          <span class="globe">🌐</span>
        </div>
      </div>
      <div class="copyright">© 1999 - 2026 PayPal。僅供課堂練習用途。</div>
    </footer>
  </div>
</template>

<style scoped>
.choose-page {
  min-height: 100vh;
  background: #f5f5f5;
  display: flex;
  flex-direction: column;
}

/* Header */
.choose-header {
  background: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 32px;
  border-bottom: 1px solid #e5e8eb;
}

.logo {
  height: 28px;
  cursor: pointer;
}

.btn-login {
  padding: 8px 22px;
  border: 1.5px solid var(--paypal-blue);
  border-radius: 999px;
  background: #fff;
  color: var(--paypal-blue);
  font-size: 15px;
  font-weight: 700;
  cursor: pointer;
  font-family: inherit;
  transition: all 0.2s;
}

.btn-login:hover {
  background: rgba(0, 112, 186, 0.06);
}

/* Main */
.choose-main {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 48px 20px 40px;
}

.choose-main h1 {
  font-size: clamp(22px, 3vw, 34px);
  font-weight: 400;
  color: var(--text-dark);
  margin-bottom: 10px;
  text-align: center;
}

.subtitle {
  font-size: 15px;
  color: var(--text-light);
  margin-bottom: 36px;
  text-align: center;
}

.cards {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
  justify-content: center;
  width: 100%;
  max-width: 860px;
}

.account-card {
  background: #fff;
  border: 1px solid #e0e3e7;
  border-radius: 8px;
  padding: 36px 32px 40px;
  flex: 1;
  min-width: 280px;
  max-width: 380px;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.account-card h2 {
  font-size: 18px;
  font-weight: 700;
  color: var(--text-dark);
  margin-bottom: 20px;
}

.btn-register {
  width: 100%;
  padding: 12px;
  background: var(--paypal-blue);
  color: #fff;
  border: none;
  border-radius: 999px;
  font-size: 16px;
  font-weight: 700;
  cursor: pointer;
  font-family: inherit;
  margin-bottom: 24px;
  transition: background 0.2s;
}

.btn-register:hover {
  background: var(--paypal-dark);
}

.account-card ul {
  list-style: disc;
  padding-left: 18px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.account-card ul li {
  font-size: 14px;
  color: var(--text-dark);
  line-height: 1.5;
}

/* Footer */
.choose-footer {
  background: #f5f5f5;
  padding: 24px 32px 16px;
  border-top: 1px solid #dde0e3;
}

.footer-links {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
  margin-bottom: 12px;
}

.footer-links a {
  font-size: 13px;
  color: var(--paypal-blue);
  text-decoration: none;
  font-weight: 500;
}

.footer-links a:hover { text-decoration: underline; }

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 10px;
}

.lang-right {
  font-size: 13px;
  color: var(--text-light);
  display: flex;
  align-items: center;
  gap: 4px;
}

.copyright {
  font-size: 12px;
  color: #9ea3a8;
  text-align: center;
}
</style>
