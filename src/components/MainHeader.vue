<script setup>
import { ref } from 'vue'

const emit = defineEmits(['login', 'signup'])

const activeMenu = ref(null)

const toggleMenu = (menuName) => {
  if (activeMenu.value === menuName) {
    activeMenu.value = null
  } else {
    activeMenu.value = menuName
  }
}

const closeMenu = () => {
  activeMenu.value = null
}
</script>

<template>
  <header class="main-header">
    <div class="nav-wrap">
      <div class="nav-left">
        <a class="logo" href="#" aria-label="PayPal 首頁" @click="closeMenu">
          <img src="/image/pp_fc_hl.svg" alt="PayPal">
        </a>

        <nav class="nav-links" aria-label="主選單">
          <!-- Item 1: 購物 -->
          <div 
            class="nav-item" 
            :class="{ 'is-active': activeMenu === 'shopping' }"
            @mouseenter="activeMenu = 'shopping'"
            @mouseleave="closeMenu"
          >
            <div class="nav-trigger" @click.stop="toggleMenu('shopping')">購物</div>
            <div class="mega-menu" :class="{ 'show': activeMenu === 'shopping' }">
              <div class="mega-close" @click.stop="closeMenu">×</div>
              <div class="mega-grid cols-2">
                <div class="mega-col">
                  <ul>
                    <li><a href="#">eBay 付款</a></li>
                    <li><a href="#">網站付款</a></li>
                  </ul>
                </div>
                <div class="mega-col">
                  <ul>
                    <li><a href="#">手機支付</a></li>
                    <li><a href="#">更多 PayPal 服務</a></li>
                  </ul>
                </div>
              </div>
            </div>
          </div>

          <!-- Item 2: 商業銷售解決方案 -->
          <div 
            class="nav-item" 
            :class="{ 'is-active': activeMenu === 'business' }"
            @mouseenter="activeMenu = 'business'"
            @mouseleave="closeMenu"
          >
            <div class="nav-trigger" @click.stop="toggleMenu('business')">商業銷售解決方案</div>
            <div class="mega-menu" :class="{ 'show': activeMenu === 'business' }">
              <div class="mega-close" @click.stop="closeMenu">×</div>
              <div class="mega-grid cols-3">
                <div class="mega-col">
                  <h4>中小企業</h4>
                  <ul>
                    <li><a href="#">簡介</a></li>
                    <li><a href="#">立即開始</a></li>
                  </ul>
                </div>
                <div class="mega-col">
                  <h4>企業</h4>
                  <ul>
                    <li><a href="#">平台與解決方案</a></li>
                    <li><a href="#">接受付款</a></li>
                    <li><a href="#">進行付款</a></li>
                    <li><a href="#">風險管理</a></li>
                    <li><a href="#">簡化作業</a></li>
                  </ul>
                </div>
                <div class="mega-col">
                  <h4>其他詳情</h4>
                  <ul>
                    <li><a href="#">價目方案</a></li>
                  </ul>
                </div>
              </div>
            </div>
          </div>

          <!-- Item 3: 銷售 -->
          <div 
            class="nav-item" 
            :class="{ 'is-active': activeMenu === 'selling' }"
            @mouseenter="activeMenu = 'selling'"
            @mouseleave="closeMenu"
          >
            <div class="nav-trigger" @click.stop="toggleMenu('selling')">銷售</div>
            <div class="mega-menu" :class="{ 'show': activeMenu === 'selling' }">
              <div class="mega-close" @click.stop="closeMenu">×</div>
              <div class="mega-grid cols-2">
                <div class="mega-col">
                  <ul>
                    <li><a href="#">在你的網站上接受付款</a></li>
                    <li><a href="#">電郵發送電子帳單</a></li>
                  </ul>
                </div>
                <div class="mega-col">
                  <ul>
                    <li><a href="#">你的企業解決方案</a></li>
                    <li><a href="#">要求付款</a></li>
                  </ul>
                </div>
              </div>
            </div>
          </div>

          <!-- Item 4: 付款 -->
          <div class="nav-item">
            <div class="nav-trigger no-dropdown"><a href="#">付款</a></div>
          </div>
        </nav>
      </div>

      <div class="header-actions">
        <button class="btn-outline" @click="emit('login')">登入</button>
        <button class="btn-solid" @click="emit('signup')">註冊</button>
      </div>
    </div>
  </header>
</template>

<style scoped>
.main-header {
  position: sticky;
  top: 0;
  z-index: 50;
  background: #fff;
  border-bottom: 1px solid #e5e8eb;
}

.nav-wrap {
  max-width: var(--container);
  margin: 0 auto;
  padding: 0 18px;
  min-height: 72px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
}

.nav-left {
  display: flex;
  align-items: center;
  gap: 28px;
}

.logo {
  width: 150px;
  display: flex;
  align-items: center;
}

.logo img {
  width: 100%;
  height: auto;
}

.nav-links {
  display: flex;
  align-items: center;
}

.nav-item {
  position: relative;
}

.nav-trigger {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 26px 20px;
  font-size: 15px;
  font-weight: 700;
  color: #1f2733;
  cursor: pointer;
  user-select: none;
  transition: color 0.2s ease;
}

.nav-trigger::after {
  content: "⌄";
  font-size: 13px;
  color: #7c8591;
  transform: translateY(-1px);
  transition: transform 0.25s ease;
}

.nav-trigger.no-dropdown::after {
  display: none;
}

.nav-item:hover .nav-trigger,
.nav-item.is-active .nav-trigger {
  color: var(--paypal-blue);
}

.nav-item:hover .nav-trigger::after,
.nav-item.is-active .nav-trigger::after {
  transform: rotate(180deg) translateY(1px);
  color: var(--paypal-blue);
}

.mega-menu {
  display: none;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: max-content;
  min-width: 500px;
  background: var(--menu-blue);
  color: #fff;
  padding: 36px 28px 44px;
  border-radius: 0 0 8px 8px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
  z-index: 100;
}

/* Specific wide mega-menu for cols-3 */
.nav-item:nth-child(2) .mega-menu {
  min-width: 700px;
}

.nav-item:hover .mega-menu,
.mega-menu.show {
  display: block;
}

.mega-close {
  position: absolute;
  right: 20px;
  top: 10px;
  font-size: 28px;
  font-weight: 300;
  color: #fff;
  opacity: 0.7;
  cursor: pointer;
  transition: opacity 0.2s ease;
}

.mega-close:hover {
  opacity: 1;
}

.mega-grid {
  display: grid;
  gap: 32px;
}

.mega-grid.cols-2 {
  grid-template-columns: repeat(2, minmax(200px, 1fr));
}

.mega-grid.cols-3 {
  grid-template-columns: repeat(3, minmax(180px, 1fr));
}

.mega-col h4 {
  font-size: 16px;
  margin-bottom: 12px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  padding-bottom: 6px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.mega-col ul {
  list-style: none;
}

.mega-col li {
  font-size: 15px;
  line-height: 1.8;
  font-weight: 600;
  margin-bottom: 4px;
}

.mega-col li a {
  color: rgba(255, 255, 255, 0.85);
  transition: color 0.2s ease;
}

.mega-col li a:hover {
  color: #fff;
  text-decoration: underline;
}

.header-actions {
  display: flex;
  gap: 10px;
  align-items: center;
}

/* Responsive CSS Styles */
@media (max-width: 1080px) {
  .nav-trigger {
    font-size: 14px;
    padding: 24px 14px;
  }

  .mega-menu {
    min-width: 450px;
  }
  
  .nav-item:nth-child(2) .mega-menu {
    min-width: 600px;
  }
}

@media (max-width: 920px) {
  .main-header {
    position: static;
  }

  .nav-wrap {
    flex-direction: column;
    align-items: stretch;
    padding: 12px 14px;
    gap: 10px;
  }

  .nav-left {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }

  .logo {
    width: 130px;
  }

  .nav-links {
    width: 100%;
    flex-wrap: wrap;
    row-gap: 4px;
  }

  .nav-item {
    width: 100%;
  }

  .nav-trigger {
    width: 100%;
    font-size: 14px;
    padding: 10px 10px;
    display: flex;
    justify-content: space-between;
  }

  .mega-menu {
    position: static;
    transform: none;
    width: 100% !important;
    min-width: 0 !important;
    border-radius: 12px;
    margin: 6px 0 10px;
    padding: 16px;
    box-shadow: none;
  }

  .mega-grid.cols-2,
  .mega-grid.cols-3 {
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .mega-close {
    display: none;
  }

  .mega-col h4 {
    font-size: 15px;
    margin-bottom: 8px;
  }

  .mega-col li {
    font-size: 14px;
    line-height: 1.7;
  }

  .header-actions {
    width: 100%;
    justify-content: flex-end;
    margin-top: 8px;
  }

  .btn-outline,
  .btn-solid {
    padding: 8px 18px;
    font-size: 14px;
  }
}
</style>
