<script setup>
defineProps({
  theme: {
    type: String,
    default: 'light',
    validator: (value) => ['light', 'plain'].includes(value)
  },
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  buttonText: {
    type: String,
    required: true
  },
  buttonUrl: {
    type: String,
    default: '#'
  }
})

const emit = defineEmits(['click-button'])
</script>

<template>
  <section :class="['cta-container', theme === 'light' ? 'cta-light' : 'cta-plain']">
    <h2>{{ title }}</h2>
    <p>{{ description }}</p>
    <button class="btn-solid" @click="emit('click-button')">{{ buttonText }}</button>
  </section>
</template>

<style scoped>
.cta-container {
  text-align: center;
  width: 100%;
}

.cta-light {
  background: #f3f4f6;
  padding: 74px 18px;
}

.cta-plain {
  background: #f6f7f8;
  padding: 70px 18px 50px;
}

h2 {
  font-size: clamp(30px, 2.5vw, 42px);
  margin-bottom: 14px;
  font-weight: 500;
  color: #4a515b;
}

p {
  color: #6a717b;
  margin-bottom: 24px;
  font-size: 17px;
}

@media (max-width: 920px) {
  .cta-light,
  .cta-plain {
    padding-top: 46px;
    padding-bottom: 46px;
  }

  h2 {
    font-size: 28px;
  }

  p {
    font-size: 16px;
  }
}
</style>
