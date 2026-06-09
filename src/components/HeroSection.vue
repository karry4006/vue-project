<template>
  <section class="hero">
    <div class="hero-inner">
      <div class="hero-copy">
        <h1>「買家購物安全保障」讓你跨國購物輕鬆無憂</h1>
        <p>有了 PayPal 的保障，你可以更安心在台灣享受跨國購物樂趣。</p>
        <button class="btn-solid hero-btn">立即註冊</button>
        <div class="hero-link">
          <a href="#">進一步了解「買家購物安全保障」</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 420px;
  background-image: linear-gradient(to right, rgba(255, 255, 255, 0.92) 0%, rgba(255, 255, 255, 0.65) 45%, rgba(255, 255, 255, 0.05) 70%), url("/image/home_n2_1x.jpg");
  background-position: center;
  background-size: cover;
  display: flex;
  align-items: center;
}

.hero-inner {
  max-width: var(--container);
  margin: 0 auto;
  width: 100%;
  padding: 28px 18px;
}

.hero-copy {
  max-width: 480px;
}

.hero h1 {
  font-size: clamp(32px, 3vw, 48px);
  line-height: 1.25;
  color: #484b50;
  margin-bottom: 18px;
  font-weight: 500;
}

.hero p {
  font-size: 20px;
  color: #5f6368;
  margin-bottom: 22px;
}

.hero .hero-btn {
  padding: 12px 40px;
  font-size: 18px;
}

.hero-link {
  margin-top: 14px;
  color: var(--paypal-blue);
  font-weight: 700;
  font-size: 14px;
}

.hero-link a {
  color: var(--paypal-blue);
  text-decoration: none;
}

.hero-link a:hover {
  text-decoration: underline;
}

@media (max-width: 920px) {
  .hero {
    min-height: 360px;
    background-position: 64% center;
    padding: 30px 0;
  }

  .hero h1 {
    font-size: 28px;
  }

  .hero p {
    font-size: 16px;
  }
}
</style>
