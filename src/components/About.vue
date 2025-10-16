<!-- 响应式关于我们 -->
<template>
  <section class="about" id="about">
    <div class="container">
      <div class="section-header">
        <h2>关于我们</h2>
        <p>20年专业物流经验，值得信赖的合作伙伴</p>
      </div>
      
      <div class="about-content">
        <div class="about-text">
          <h3>专业物流服务20年</h3>
          <p>
            速达物流成立于2004年，致力于为客户提供高效、安全、可靠的物流解决方案。
            我们拥有覆盖全球的物流网络和专业的团队，为客户的事业发展保驾护航。
          </p>
          
          <div class="company-stats">
            <div class="company-stat">
              <h4>2004年</h4>
              <p>成立时间</p>
            </div>
            <div class="company-stat">
              <h4>5000+</h4>
              <p>专业员工</p>
            </div>
            <div class="company-stat">
              <h4>100万+</h4>
              <p>满意客户</p>
            </div>
          </div>
          
          <div class="features-grid">
            <div class="feature-item">
              <div class="feature-icon">🎯</div>
              <div class="feature-content">
                <h4>我们的使命</h4>
                <p>通过创新的物流解决方案，连接世界，创造价值，让物流更简单、更高效。</p>
              </div>
            </div>
            <div class="feature-item">
              <div class="feature-icon">🌟</div>
              <div class="feature-content">
                <h4>我们的愿景</h4>
                <p>成为全球领先的智慧物流服务提供商，引领行业创新发展。</p>
              </div>
            </div>
            <div class="feature-item">
              <div class="feature-icon">💎</div>
              <div class="feature-content">
                <h4>核心价值观</h4>
                <p>客户至上、诚信为本、创新驱动、合作共赢。</p>
              </div>
            </div>
          </div>
        </div>
        
        <div class="about-visual">
          <div class="visual-container">
            <div class="map-visual">
              <div class="map-point" style="top: 30%; left: 20%;">北京</div>
              <div class="map-point" style="top: 40%; left: 50%;">上海</div>
              <div class="map-point" style="top: 60%; left: 45%;">广州</div>
              <div class="map-point" style="top: 35%; left: 75%;">东京</div>
              <div class="map-point" style="top: 50%; left: 15%;">纽约</div>
              <div class="connection-line" v-for="line in connectionLines" 
                   :key="line.id" :style="line.style"></div>
            </div>
          </div>
          
          <div class="achievements">
            <div class="achievement">
              <div class="achievement-icon">🏆</div>
              <div class="achievement-content">
                <h5>行业认证</h5>
                <p>ISO9001质量体系认证</p>
              </div>
            </div>
            <div class="achievement">
              <div class="achievement-icon">⭐</div>
              <div class="achievement-content">
                <h5>客户评价</h5>
                <p>98%客户满意度</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const connectionLines = ref([
  { id: 1, style: 'top: 35%; left: 25%; width: 25%; transform: rotate(15deg);' },
  { id: 2, style: 'top: 45%; left: 35%; width: 15%; transform: rotate(-10deg);' },
  { id: 3, style: 'top: 50%; left: 20%; width: 30%; transform: rotate(25deg);' }
])
</script>

<style scoped>
.about {
  padding: 80px 0;
  background: #f8f9fa;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.about-text h3 {
  color: #2c5aa0;
  margin-bottom: 1.5rem;
  font-size: 2rem;
}

.about-text p {
  line-height: 1.8;
  color: #666;
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

.company-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  margin: 2rem 0;
  padding: 2rem;
  background: white;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
}

.company-stat {
  text-align: center;
}

.company-stat h4 {
  color: #ff6b35;
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.company-stat p {
  color: #666;
  margin: 0;
  font-size: 0.9rem;
}

.features-grid {
  display: grid;
  gap: 1.5rem;
  margin-top: 2rem;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1.5rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s;
}

.feature-item:hover {
  transform: translateX(5px);
}

.feature-icon {
  font-size: 2rem;
  flex-shrink: 0;
}

.feature-content h4 {
  color: #333;
  margin-bottom: 0.5rem;
}

.feature-content p {
  color: #666;
  margin: 0;
  line-height: 1.6;
}

.about-visual {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.visual-container {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
}

.map-visual {
  position: relative;
  height: 300px;
  background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%);
  border-radius: 10px;
  overflow: hidden;
}

.map-point {
  position: absolute;
  background: #ff6b35;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
  box-shadow: 0 3px 10px rgba(255, 107, 53, 0.3);
}

.connection-line {
  position: absolute;
  height: 2px;
  background: #ff6b35;
  opacity: 0.6;
}

.achievements {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.achievement {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
}

.achievement-icon {
  font-size: 2rem;
}

.achievement-content h5 {
  color: #333;
  margin-bottom: 0.25rem;
}

.achievement-content p {
  color: #666;
  margin: 0;
  font-size: 0.9rem;
}

/* 平板端响应式 */
@media (max-width: 1024px) {
  .about-content {
    gap: 3rem;
  }
  
  .company-stats {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
}

/* 移动端响应式 */
@media (max-width: 768px) {
  .about {
    padding: 60px 0;
  }
  
  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .about-text h3 {
    font-size: 1.5rem;
  }
  
  .company-stats {
    padding: 1.5rem;
    gap: 1rem;
  }
  
  .company-stat h4 {
    font-size: 1.5rem;
  }
  
  .feature-item {
    padding: 1rem;
  }
  
  .visual-container {
    padding: 1.5rem;
  }
  
  .map-visual {
    height: 250px;
  }
  
  .achievements {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .feature-item {
    flex-direction: column;
    text-align: center;
  }
  
  .map-point {
    padding: 0.25rem 0.5rem;
    font-size: 0.7rem;
  }
}
</style>