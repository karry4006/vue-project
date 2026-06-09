<template>
  <footer class="footer">
    <div class="footer-inner">
      <div class="footer-links">
        <a href="#">查詢中心</a>
        <a href="#">聯絡我們</a>
        <a href="#">費用</a>
        <a href="#">交易安全</a>
        <a href="#">全球購物優惠</a>
      </div>
      <div class="footer-meta">
        <nav class="footer-links no-margin">
          <a href="#">關於 PayPal</a>
          <a href="#">新聞中心</a>
          <a href="#">合作夥伴</a>
          <a href="#">隱私權聲明</a>
          <a href="#">法律同意書</a>
        </nav>
        <div class="lang-selector">
          <a href="#">English</a>
        </div>
      </div>
      <div class="copyright">
        © 1999 - 2026 PayPal。僅供課堂 wireframe 與前端練習用途。
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #f6f7f8;
  padding: 20px 18px 44px;
  color: #6f757e;
  width: 100%;
}

.footer-inner {
  max-width: var(--container);
  margin: 0 auto;
  border-top: 1px solid #d4d9de;
  padding-top: 16px;
}

.footer-links {
  display: flex;
  flex-wrap: wrap;
  gap: 18px;
  font-size: 14px;
  margin-bottom: 12px;
}

.footer-links.no-margin {
  margin-bottom: 0;
}

.footer-links a {
  color: #6f757e;
  text-decoration: none;
  font-weight: 600;
  transition: color 0.2s ease;
}

.footer-links a:hover {
  color: var(--paypal-blue);
  text-decoration: underline;
}

.footer-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 18px;
  margin-bottom: 12px;
}

.lang-selector a {
  color: #6f757e;
  text-decoration: none;
  font-weight: 600;
}

.lang-selector a:hover {
  color: var(--paypal-blue);
  text-decoration: underline;
}

.copyright {
  font-size: 12px;
  color: #8a919b;
  margin-top: 8px;
}

@media (max-width: 920px) {
  .footer-meta {
    flex-direction: column;
    align-items: flex-start;
    gap: 12px;
  }
}
</style>
