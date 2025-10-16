<!-- 响应式物流追踪 -->
<template>
  <section class="tracking" id="tracking">
    <div class="container">
      <div class="section-header">
        <h2>物流追踪</h2>
        <p>实时查询您的包裹位置和状态</p>
      </div>
      
      <div class="tracking-content">
        <div class="tracking-form-container">
          <div class="tracking-form">
            <h3>查询物流信息</h3>
            <form @submit.prevent="trackPackage">
              <div class="input-group">
                <input 
                  type="text" 
                  v-model="trackingNumber"
                  placeholder="请输入运单号"
                  required
                  class="tracking-input"
                >
                <button type="submit" class="btn btn-primary tracking-btn">
                  <span class="desktop-only">查询</span>
                  <span class="mobile-only">🔍</span>
                </button>
              </div>
            </form>
            
            <div class="tracking-examples">
              <p>示例运单号：</p>
              <div class="example-numbers">
                <span v-for="example in exampleNumbers" :key="example" 
                      @click="trackingNumber = example" class="example-number">
                  {{ example }}
                </span>
              </div>
            </div>
          </div>
        </div>
        
        <div class="tracking-result" v-if="showTrackingInfo">
          <div class="result-header">
            <h4>物流信息</h4>
            <div class="package-info">
              <p><strong>运单号：</strong>{{ trackingNumber }}</p>
              <p><strong>状态：</strong><span class="status delivered" v-if="isDelivered">已签收</span>
                <span class="status in-transit" v-else>运输中</span></p>
            </div>
          </div>
          
          <div class="tracking-steps">
            <div 
              class="step" 
              v-for="(step, index) in trackingSteps" 
              :key="index"
              :class="{ 
                active: step.active, 
                completed: step.completed,
                'last-step': index === trackingSteps.length - 1
              }"
            >
              <div class="step-marker">
                <div class="step-dot"></div>
                <div class="step-line" v-if="index !== trackingSteps.length - 1"></div>
              </div>
              <div class="step-content">
                <p class="step-title">{{ step.title }}</p>
                <p class="step-time">{{ step.time }}</p>
                <p class="step-location">{{ step.location }}</p>
                <p class="step-description" v-if="step.description">{{ step.description }}</p>
              </div>
            </div>
          </div>
        </div>
        
        <div class="tracking-features">
          <div class="feature">
            <div class="feature-icon">📱</div>
            <h4>手机推送</h4>
            <p>重要状态变化实时推送</p>
          </div>
          <div class="feature">
            <div class="feature-icon">🌐</div>
            <h4>多平台同步</h4>
            <p>网站、小程序、APP数据同步</p>
          </div>
          <div class="feature">
            <div class="feature-icon">⏰</div>
            <h4>预计到达</h4>
            <p>智能预测包裹到达时间</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const trackingNumber = ref('')
const showTrackingInfo = ref(false)
const isDelivered = ref(false)

const exampleNumbers = ref(['SD123456789', 'SD987654321', 'SD456789123'])

const trackingSteps = ref([
  {
    title: '订单已创建',
    time: '2024-01-15 08:30',
    location: '北京分拨中心',
    description: '包裹已揽收，等待发往分拨中心',
    completed: true,
    active: false
  },
  {
    title: '已揽收',
    time: '2024-01-15 09:30',
    location: '北京分拨中心',
    description: '快递员已取件，正在发往分拨中心',
    completed: true,
    active: false
  },
  {
    title: '运输中',
    time: '2024-01-15 14:20',
    location: '北京 → 上海',
    description: '包裹正在运输途中，预计明天到达',
    completed: true,
    active: false
  },
  {
    title: '到达目的地',
    time: '2024-01-16 08:15',
    location: '上海分拨中心',
    description: '包裹已到达目的地分拨中心',
    completed: true,
    active: false
  },
  {
    title: '派送中',
    time: '预计今天 14:00-16:00',
    location: '上海浦东新区',
    description: '快递员正在派件，请保持电话畅通',
    completed: false,
    active: true
  },
  {
    title: '已签收',
    time: '',
    location: '',
    description: '',
    completed: false,
    active: false
  }
])

const trackPackage = () => {
  if (trackingNumber.value) {
    showTrackingInfo.value = true
    // 模拟API调用延迟
    setTimeout(() => {
      // 在实际项目中这里会调用真实的API
    }, 500)
  }
}
</script>

<style scoped>
.tracking {
  padding: 80px 0;
  background: white;
}

.tracking-content {
  display: grid;
  gap: 3rem;
}

.tracking-form-container {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 3rem;
  border-radius: 20px;
  color: white;
}

.tracking-form h3 {
  margin-bottom: 1.5rem;
  font-size: 1.8rem;
}

.input-group {
  display: flex;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.tracking-input {
  flex: 1;
  padding: 15px 20px;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  outline: none;
}

.tracking-btn {
  padding: 15px 30px;
  white-space: nowrap;
}

.tracking-examples p {
  margin-bottom: 0.5rem;
  opacity: 0.9;
}

.example-numbers {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.example-number {
  background: rgba(255, 255, 255, 0.2);
  padding: 0.5rem 1rem;
  border-radius: 20px;
  cursor: pointer;
  transition: background 0.3s;
  font-size: 0.9rem;
}

.example-number:hover {
  background: rgba(255, 255, 255, 0.3);
}

.tracking-result {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 15px;
  border: 1px solid #e9ecef;
}

.result-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
  flex-wrap: wrap;
  gap: 1rem;
}

.result-header h4 {
  color: #333;
  margin: 0;
}

.package-info {
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
}

.package-info p {
  margin: 0;
  color: #666;
}

.status {
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
}

.status.delivered {
  background: #d4edda;
  color: #155724;
}

.status.in-transit {
  background: #fff3cd;
  color: #856404;
}

.tracking-steps {
  position: relative;
}

.step {
  display: flex;
  margin-bottom: 2rem;
  position: relative;
}

.step:last-child {
  margin-bottom: 0;
}

.step-marker {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-right: 1.5rem;
}

.step-dot {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #e0e0e0;
  position: relative;
  z-index: 2;
  border: 3px solid white;
}

.step-line {
  flex: 1;
  width: 2px;
  background: #e0e0e0;
  margin-top: 0.5rem;
}

.step.completed .step-dot {
  background: #4caf50;
}

.step.active .step-dot {
  background: #ff6b35;
  box-shadow: 0 0 0 3px rgba(255, 107, 53, 0.3);
}

.step.completed .step-line {
  background: #4caf50;
}

.step-content {
  flex: 1;
  padding-bottom: 2rem;
}

.step:last-child .step-content {
  padding-bottom: 0;
}

.step-title {
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #333;
  font-size: 1.1rem;
}

.step-time {
  color: #ff6b35;
  font-weight: 600;
  margin-bottom: 0.25rem;
}

.step-location {
  color: #666;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.step-description {
  color: #888;
  font-size: 0.9rem;
  line-height: 1.4;
}

.tracking-features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.feature {
  text-align: center;
  padding: 2rem 1rem;
  background: #f8f9fa;
  border-radius: 10px;
  transition: transform 0.3s;
}

.feature:hover {
  transform: translateY(-5px);
}

.feature-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.feature h4 {
  color: #333;
  margin-bottom: 0.5rem;
}

.feature p {
  color: #666;
  margin: 0;
}

/* 平板端响应式 */
@media (max-width: 1024px) {
  .result-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .package-info {
    gap: 1rem;
  }
}

/* 移动端响应式 */
@media (max-width: 768px) {
  .tracking {
    padding: 60px 0;
  }
  
  .tracking-form-container {
    padding: 2rem 1.5rem;
  }
  
  .input-group {
    flex-direction: column;
  }
  
  .tracking-btn {
    width: 100%;
  }
  
  .example-numbers {
    flex-direction: column;
    gap: 0.5rem;
  }
  
  .example-number {
    text-align: center;
  }
  
  .tracking-result {
    padding: 1.5rem;
  }
  
  .step {
    margin-bottom: 1.5rem;
  }
  
  .step-marker {
    margin-right: 1rem;
  }
  
  .step-content {
    padding-bottom: 1.5rem;
  }
  
  .tracking-features {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .feature {
    padding: 1.5rem 1rem;
  }
}

@media (max-width: 480px) {
  .tracking-form h3 {
    font-size: 1.5rem;
  }
  
  .step-title {
    font-size: 1rem;
  }
}
</style>