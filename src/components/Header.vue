<template>
  <header class="header" :class="{ 'scrolled': isScrolled, 'menu-open': isMenuOpen }">
    <div class="container">
      <nav class="nav">
        <div class="logo">
          <h2>深圳时必达国际物流</h2>
        </div>
        
        <!-- 桌面端导航 -->
        <ul class="nav-links desktop-nav">
          <li><a href="#home" @click="closeMenu">首页</a></li>
          <li><a href="#services" @click="closeMenu">服务</a></li>
          <li><a href="#tracking" @click="closeMenu">物流追踪</a></li>
          <li><a href="#about" @click="closeMenu">关于我们</a></li>
          <li><a href="#contact" @click="closeMenu">联系我们</a></li>
        </ul>
        
        <!-- 移动端菜单按钮 -->
        <button class="mobile-menu-btn" @click="toggleMenu" aria-label="切换菜单">
          <span></span>
          <span></span>
          <span></span>
        </button>
        
        <!-- 移动端导航 -->
        <div class="mobile-nav" :class="{ 'active': isMenuOpen }">
          <ul class="mobile-nav-links">
            <li><a href="#home" @click="closeMenu">首页</a></li>
            <li><a href="#services" @click="closeMenu">服务</a></li>
            <li><a href="#tracking" @click="closeMenu">物流追踪</a></li>
            <li><a href="#about" @click="closeMenu">关于我们</a></li>
            <li><a href="#contact" @click="closeMenu">联系我们</a></li>
          </ul>
          
          <div class="mobile-contact">
            <p>📞 400-123-4567</p>
            <p>🕒 周一至周日 8:00-22:00</p>
          </div>
        </div>
        
        <!-- 移动端菜单遮罩 -->
        <div class="mobile-overlay" :class="{ 'active': isMenuOpen }" @click="closeMenu"></div>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
  // 防止背景滚动
  document.body.style.overflow = isMenuOpen.value ? 'hidden' : 'auto'
}

const closeMenu = () => {
  isMenuOpen.value = false
  document.body.style.overflow = 'auto'
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.header {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  transition: all 0.3s ease;
}

.header.scrolled {
  background: rgba(255, 255, 255, 0.98);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo h2 {
  color: #2c5aa0;
  margin: 0;
  font-size: 1.5rem;
}

/* 桌面端导航 */
.desktop-nav {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
}

.desktop-nav a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  transition: color 0.3s;
  padding: 0.5rem 1rem;
  border-radius: 5px;
}

.desktop-nav a:hover {
  color: #2c5aa0;
  background: rgba(44, 90, 160, 0.1);
}

/* 移动端菜单按钮 */
.mobile-menu-btn {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  gap: 4px;
}

.mobile-menu-btn span {
  width: 25px;
  height: 3px;
  background: #333;
  transition: all 0.3s ease;
}

/* 移动端导航 */
.mobile-nav {
  position: fixed;
  top: 0;
  right: -100%;
  width: 80%;
  max-width: 300px;
  height: 100vh;
  background: white;
  box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
  padding: 2rem;
  transition: right 0.3s ease;
  z-index: 1001;
  display: flex;
  flex-direction: column;
}

.mobile-nav.active {
  right: 0;
}

.mobile-nav-links {
  list-style: none;
  margin-bottom: 2rem;
}

.mobile-nav-links li {
  margin-bottom: 1rem;
}

.mobile-nav-links a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  font-size: 1.1rem;
  display: block;
  padding: 0.75rem 0;
  border-bottom: 1px solid #eee;
}

.mobile-contact {
  margin-top: auto;
  padding-top: 2rem;
  border-top: 1px solid #eee;
}

.mobile-contact p {
  margin-bottom: 0.5rem;
  color: #666;
}

/* 移动端遮罩 */
.mobile-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
  z-index: 1000;
}

.mobile-overlay.active {
  opacity: 1;
  visibility: visible;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .desktop-nav {
    display: none;
  }
  
  .mobile-menu-btn {
    display: flex;
  }
  
  .logo h2 {
    font-size: 1.3rem;
  }
}

@media (max-width: 480px) {
  .mobile-nav {
    width: 85%;
  }
}
</style>