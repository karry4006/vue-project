<template>
  <section class="section">
    <div class="section-inner section-two-col">
      <div class="media-container">
        <img class="media-img" src="/image/tw-app-new.jpg" alt="PayPal 手機應用程式">
      </div>
      <div class="copy">
        <h2>電子支付 快速便利</h2>
        <p>全方位掌握數位支付流程，隨時檢視付款與餘額，讓交易更有效率。</p>
        <div class="link-group">
          <a class="text-link" href="#">eBay 購物</a>
          <a class="text-link" href="#">網店購物</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.section {
  padding: 72px 18px;
  background: #fff;
}

.section-inner {
  max-width: var(--container);
  margin: 0 auto;
  display: grid;
  align-items: center;
  gap: 42px;
}

.section-two-col {
  grid-template-columns: 1fr 1fr;
}

.media-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.media-img {
  width: 100%;
  max-width: 280px;
  display: block;
  border-radius: 6px;
}

.copy h2 {
  font-size: clamp(30px, 2.4vw, 44px);
  margin-bottom: 14px;
  color: #434a55;
  font-weight: 500;
}

.copy p {
  color: var(--text-light);
  font-size: 18px;
  margin-bottom: 14px;
}

.link-group {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
}

.text-link {
  color: var(--paypal-blue);
  font-weight: 700;
  font-size: 16px;
  text-decoration: none;
}

.text-link:hover {
  text-decoration: underline;
}

@media (max-width: 920px) {
  .section {
    padding-top: 46px;
    padding-bottom: 46px;
  }

  .section-two-col {
    grid-template-columns: 1fr;
    gap: 24px;
  }

  .copy h2 {
    font-size: 28px;
    text-align: center;
  }

  .copy p {
    font-size: 16px;
    text-align: center;
  }

  .link-group {
    justify-content: center;
  }
}
</style>
