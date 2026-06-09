<script setup>
defineProps({
  bgImage: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  linkText: {
    type: String,
    required: true
  },
  linkUrl: {
    type: String,
    default: '#'
  }
})
</script>

<template>
  <section class="image-banner" :style="{ backgroundImage: `url(${bgImage})` }">
    <div class="section-inner">
      <div class="copy">
        <h2>{{ title }}</h2>
        <p>{{ description }}</p>
        <a class="text-link" :href="linkUrl">{{ linkText }}</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.image-banner {
  min-height: 360px;
  background-size: cover;
  background-position: center;
  position: relative;
  display: flex;
  align-items: center;
  width: 100%;
}

.image-banner::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.3) 45%, rgba(0, 0, 0, 0.15) 100%);
  z-index: 1;
}

.section-inner {
  max-width: var(--container);
  margin: 0 auto;
  width: 100%;
  padding: 28px 18px;
  position: relative;
  z-index: 2;
}

.copy {
  max-width: 520px;
}

.copy h2 {
  font-size: clamp(30px, 2.4vw, 44px);
  margin-bottom: 14px;
  color: #fff;
  font-weight: 500;
}

.copy p {
  color: rgba(255, 255, 255, 0.9);
  font-size: 18px;
  margin-bottom: 14px;
  line-height: 1.5;
}

.text-link {
  color: #fff;
  font-weight: 700;
  font-size: 16px;
  text-decoration: none;
  border-bottom: 2px solid transparent;
  padding-bottom: 2px;
  transition: border-color 0.2s ease;
  display: inline-block;
}

.text-link:hover {
  border-color: #fff;
}

@media (max-width: 920px) {
  .image-banner {
    min-height: 300px;
  }

  .copy h2 {
    font-size: 28px;
  }

  .copy p {
    font-size: 16px;
  }
}
</style>
