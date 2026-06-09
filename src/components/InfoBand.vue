<template>
  <section class="blue-band">
    <div class="section-inner">
      <div class="info-col">
        <h3>電子支付 快速便利</h3>
        <p>你只需要漂亮的電子郵件地址，就可以更輕鬆又更安全地為新用戶提供商品或服務付款服務。</p>
        <a class="text-link" href="#">支付轉帳教學</a>
      </div>
      <div class="info-col">
        <h3>輕鬆要求買家支付交易款項</h3>
        <p>在完成銷售後，你可以快速發出付款要求給你的買家，買家收到後即可透過 PayPal 完成付款流程。</p>
        <a class="text-link" href="#">要求支付交易款項</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.blue-band {
  background: var(--paypal-dark);
  color: #fff;
  padding: 54px 18px;
}

.blue-band .section-inner {
  max-width: var(--container);
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 54px;
}

.info-col {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.blue-band h3 {
  font-size: clamp(28px, 2.2vw, 38px);
  margin-bottom: 12px;
  font-weight: 500;
  color: #fff;
}

.blue-band p {
  font-size: 17px;
  line-height: 1.65;
  color: #d7e5ff;
  margin-bottom: 12px;
}

.text-link {
  color: #fff;
  font-weight: 700;
  font-size: 16px;
  text-decoration: none;
  border-bottom: 2px solid transparent;
  padding-bottom: 2px;
  transition: border-color 0.2s ease;
}

.text-link:hover {
  border-color: #fff;
}

@media (max-width: 920px) {
  .blue-band {
    padding-top: 46px;
    padding-bottom: 46px;
  }

  .blue-band .section-inner {
    grid-template-columns: 1fr;
    gap: 32px;
  }

  .blue-band h3 {
    font-size: 28px;
  }

  .blue-band p {
    font-size: 16px;
  }
}
</style>
