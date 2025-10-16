<!-- 首页大图 -->
<template>
  <section class="hero" id="home">
    <div class="container">
      <div class="hero-content">
        <div class="hero-text">
          <h1>专业物流解决方案</h1>
          <p>快速、安全、可靠的全球物流服务，为您的事业加速。覆盖全国2000+城市，直达全球100+国家。</p>
          <div class="hero-buttons">
            <a href="#tracking" class="btn btn-primary">物流追踪</a>
            <a href="#contact" class="btn btn-secondary">在线咨询</a>
          </div>
        </div>
        
        <div class="hero-visual">
          <!-- 这里可以放物流相关的SVG或图片 -->
          <div class="hero-graphic">
            <div class="truck-animation">
              <div class="truck">🚚</div>
              <div class="road"></div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="hero-stats">
        <div class="stat">
          <h3>100+</h3>
          <p>覆盖国家</p>
        </div>
        <div class="stat">
          <h3>50万+</h3>
          <p>年发货量</p>
        </div>
        <div class="stat">
          <h3>99.8%</h3>
          <p>准时到达率</p>
        </div>
        <div class="stat">
          <h3>24/7</h3>
          <p>客户服务</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// 可以添加动画效果
</script>

<style scoped>
.hero {
  background: linear-gradient(135deg, #2c5aa0 0%, #1e3a8a 100%);
  color: white;
  padding: 120px 0 80px;
  margin-top: 60px;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000" opacity="0.1"><polygon points="0,1000 1000,0 1000,1000" fill="white"/></svg>');
  background-size: cover;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
  margin-bottom: 4rem;
  position: relative;
  z-index: 1;
}

.hero-text h1 {
  font-size: 3rem;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.hero-text p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.9;
  line-height: 1.6;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-graphic {
  width: 100%;
  max-width: 400px;
}

.truck-animation {
  position: relative;
  height: 200px;
}

.truck {
  font-size: 4rem;
  position: absolute;
  left: 0;
  animation: drive 3s ease-in-out infinite;
}

.road {
  position: absolute;
  bottom: 40px;
  left: 0;
  right: 0;
  height: 3px;
  background: white;
  opacity: 0.3;
}

@keyframes drive {
  0%, 100% { transform: translateX(0); }
  50% { transform: translateX(50px); }
}

.hero-stats {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  position: relative;
  z-index: 1;
}

.stat {
  text-align: center;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  backdrop-filter: blur(10px);
}

.stat h3 {
  font-size: 2.5rem;
  margin: 0;
  color: #ff6b35;
}

.stat p {
  margin: 0.5rem 0 0;
  opacity: 0.9;
  font-size: 0.9rem;
}

/* 平板端响应式 */
@media (max-width: 1024px) {
  .hero-text h1 {
    font-size: 2.5rem;
  }
  
  .hero-stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}

/* 移动端响应式 */
@media (max-width: 768px) {
  .hero {
    padding: 100px 0 60px;
  }
  
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  
  .hero-text h1 {
    font-size: 2rem;
  }
  
  .hero-text p {
    font-size: 1.1rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-buttons .btn {
    min-width: 140px;
  }
  
  .truck {
    font-size: 3rem;
  }
  
  .hero-stats {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .stat {
    padding: 1rem;
  }
  
  .stat h3 {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .hero-text h1 {
    font-size: 1.8rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .hero-buttons .btn {
    width: 100%;
    max-width: 200px;
  }
}
</style>