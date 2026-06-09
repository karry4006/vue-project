<script setup>
import PromoBar from './PromoBar.vue'
import MainHeader from './MainHeader.vue'
import HeroSection from './HeroSection.vue'
import HelpStrip from './HelpStrip.vue'
import FeatureSection from './FeatureSection.vue'
import ImageBanner from './ImageBanner.vue'
import InfoBand from './InfoBand.vue'
import CtaSection from './CtaSection.vue'
import MainFooter from './MainFooter.vue'

const emit = defineEmits(['navigate'])

function handleLogin() {
  emit('navigate', 'login')
}

function handleSignup() {
  emit('navigate', 'signup-choose')
}
</script>

<template>
  <div class="app-container">
    <PromoBar />
    <MainHeader @login="handleLogin" @signup="handleSignup" />
    <HeroSection />
    <HelpStrip />
    <FeatureSection />
    <ImageBanner
      bg-image="/image/Asia_BuyerProtection_1600x900.jpg"
      title="手機是最方便的購物平台"
      description="活用這些數位工具，讓你在任何地方都能安全快速地完成購物與付款。"
      link-text="手機購物"
    />
    <InfoBand />
    <ImageBanner
      bg-image="/image/editorial-automated-payments.jpg"
      title="輕鬆管理定時定額付款"
      description="無論是每月訂閱，還是定期代扣款，都能透過安全機制自動完成，降低管理成本。"
      link-text="了解詳情"
    />
    <CtaSection
      theme="light"
      title="需要跨境線上收款？"
      description="如果你需要跨境收款，PayPal 提供台灣的賣家更多穩定可靠的收款方式。"
      button-text="瀏覽商業解決方案"
      @click-button="handleSignup"
    />
    <CtaSection
      theme="plain"
      title="透過 PayPal 在台灣即可通行全球"
      description="立即建立帳戶，開始安全付款與收款。"
      button-text="立即註冊"
      @click-button="handleSignup"
    />
    <MainFooter />
  </div>
</template>

<style scoped>
.app-container {
  width: 100%;
  overflow-x: hidden;
  display: flex;
  flex-direction: column;
}
</style>
