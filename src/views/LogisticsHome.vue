<template>
  <div class="logistics-home">
    <Header />
    <Hero />
    <Services />
    <!-- <Tracking /> -->
    <About />
    <Contact />
    <Footer />
    
    <!-- 移动端浮动按钮 -->
    <div class="floating-actions mobile-only">
      <button class="floating-btn primary" @click="scrollToTracking">
        🔍 查快递
      </button>
      <button class="floating-btn secondary" @click="scrollToContact">
        📞 联系
      </button>
    </div>
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Hero from '@/components/Hero.vue'
import Services from '@/components/Services.vue'
import Tracking from '@/components/Tracking.vue'
import About from '@/components/About.vue'
import Contact from '@/components/Contact.vue'
import Footer from '@/components/Footer.vue'

const scrollToTracking = () => {
  document.getElementById('tracking')?.scrollIntoView({ 
    behavior: 'smooth' 
  })
}

const scrollToContact = () => {
  document.getElementById('contact')?.scrollIntoView({ 
    behavior: 'smooth' 
  })
}
</script>

<style scoped>
.logistics-home {
  min-height: 100vh;
}

/* 移动端浮动按钮 */
.floating-actions {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  z-index: 999;
}

.floating-btn {
  padding: 12px 16px;
  border: none;
  border-radius: 25px;
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 5px;
}

.floating-btn.primary {
  background: #ff6b35;
  color: white;
}

.floating-btn.secondary {
  background: white;
  color: #2c5aa0;
  border: 1px solid #2c5aa0;
}

.floating-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
}

/* 响应式设计优化 */
@media (max-width: 768px) {
  .floating-actions {
    bottom: 15px;
    right: 15px;
  }
  
  .floating-btn {
    padding: 10px 14px;
    font-size: 13px;
  }
}

@media (max-width: 480px) {
  .floating-actions {
    bottom: 10px;
    right: 10px;
  }
}
</style>