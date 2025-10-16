<!-- 服务展示 -->
<template>
  <section class="services" id="services">
    <div class="container">
      <div class="section-header">
        <h2>我们的服务</h2>
        <p>提供全方位物流解决方案，满足不同客户需求</p>
      </div>
      
      <div class="services-grid">
        <div class="service-card" v-for="service in services" :key="service.id">
          <div class="service-icon">
            <span>{{ service.icon }}</span>
          </div>
          <h3>{{ service.title }}</h3>
          <p>{{ service.description }}</p>
          <ul class="service-features">
            <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
          </ul>
          <a href="#" class="service-link">了解更多 →</a>
        </div>
      </div>
      
      <div class="services-cta">
        <h3>需要定制物流解决方案？</h3>
        <p>我们的专家团队为您提供个性化服务</p>
        <a href="#contact" class="btn btn-primary">立即咨询</a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const services = ref([
  {
    id: 1,
    icon: '🚚',
    title: '国内快递',
    description: '全国范围内的快速配送服务',
    features: ['24-48小时送达', '全国覆盖', '实时追踪', '上门取件']
  },
  {
    id: 2,
    icon: '✈️',
    title: '国际货运',
    description: '全球范围内的空运、海运服务',
    features: ['200+国家覆盖', '多种运输方式', '海关清关', '门到门服务']
  },
  {
    id: 3,
    icon: '📦',
    title: '仓储服务',
    description: '专业的仓储管理和库存优化',
    features: ['智能仓储', '库存管理', '订单处理', '定制方案']
  },
  {
    id: 4,
    icon: '🔒',
    title: '冷链物流',
    description: '温控运输服务，确保产品品质',
    features: ['全程温控', '实时监控', '专业设备', '品质保证']
  },
  {
    id: 5,
    icon: '🚛',
    title: '整车运输',
    description: '大件物品和批量货物运输',
    features: ['多种车型', '批量运输', '专业装卸', '保险服务']
  },
  {
    id: 6,
    icon: '📊',
    title: '供应链管理',
    description: '端到端的供应链优化服务',
    features: ['流程优化', '成本控制', '效率提升', '持续改进']
  }
])
</script>

<style scoped>
.services {
  padding: 80px 0;
  background: #f8f9fa;
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-header h2 {
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 1rem;
}

.section-header p {
  font-size: 1.2rem;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.service-card {
  background: white;
  padding: 2.5rem 2rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  border: 1px solid #f0f0f0;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
}

.service-icon {
  font-size: 3.5rem;
  margin-bottom: 1.5rem;
}

.service-card h3 {
  color: #2c5aa0;
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.service-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.service-features {
  list-style: none;
  margin-bottom: 2rem;
  text-align: left;
}

.service-features li {
  padding: 0.5rem 0;
  color: #555;
  position: relative;
  padding-left: 1.5rem;
}

.service-features li::before {
  content: '✓';
  color: #4caf50;
  position: absolute;
  left: 0;
  font-weight: bold;
}

.service-link {
  color: #ff6b35;
  text-decoration: none;
  font-weight: 600;
  transition: color 0.3s;
}

.service-link:hover {
  color: #e55a2b;
}

.services-cta {
  background: white;
  padding: 3rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
}

.services-cta h3 {
  color: #333;
  margin-bottom: 1rem;
  font-size: 1.8rem;
}

.services-cta p {
  color: #666;
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

/* 平板端响应式 */
@media (max-width: 1024px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* 移动端响应式 */
@media (max-width: 768px) {
  .services {
    padding: 60px 0;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .service-card {
    padding: 2rem 1.5rem;
  }
  
  .services-cta {
    padding: 2rem 1.5rem;
  }
  
  .services-cta h3 {
    font-size: 1.5rem;
  }
}

@media (max-width: 480px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .service-card {
    padding: 1.5rem;
  }
  
  .service-icon {
    font-size: 3rem;
  }
}
</style>