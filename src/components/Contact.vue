// 联系我们
<template>
  <section class="contact" id="contact">
    <div class="container">
      <div class="section-header">
        <h2>联系我们</h2>
        <p>有任何问题？我们随时为您提供帮助</p>
      </div>
      
      <div class="contact-content">
        <div class="contact-info">
          <h3>获取专业物流咨询</h3>
          <p>我们的团队随时准备为您提供个性化的物流解决方案</p>
          
          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">📞</div>
              <div class="method-content">
                <h4>电话咨询</h4>
                <p>400-123-4567</p>
                <span>周一至周日 8:00-22:00</span>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">✉️</div>
              <div class="method-content">
                <h4>邮箱联系</h4>
                <p>info@express.com</p>
                <span>24小时内回复</span>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">💬</div>
              <div class="method-content">
                <h4>在线客服</h4>
                <p>立即咨询</p>
                <span>工作时间实时响应</span>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">📍</div>
              <div class="method-content">
                <h4>公司地址</h4>
                <p>北京市朝阳区物流园区88号</p>
                <span>欢迎来访</span>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <h4>关注我们</h4>
            <div class="social-icons">
              <a href="#" class="social-icon">微信</a>
              <a href="#" class="social-icon">微博</a>
              <a href="#" class="social-icon">抖音</a>
              <a href="#" class="social-icon">知乎</a>
            </div>
          </div>
        </div>
        
        <div class="contact-form-container">
          <form class="contact-form" @submit.prevent="submitForm">
            <h3>在线留言</h3>
            
            <div class="form-group">
              <label for="name">姓名 *</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name"
                required
                placeholder="请输入您的姓名"
              >
            </div>
            
            <div class="form-row">
              <div class="form-group">
                <label for="phone">电话 *</label>
                <input 
                  type="tel" 
                  id="phone" 
                  v-model="form.phone"
                  required
                  placeholder="请输入您的电话"
                >
              </div>
              
              <div class="form-group">
                <label for="email">邮箱</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="form.email"
                  placeholder="请输入您的邮箱"
                >
              </div>
            </div>
            
            <div class="form-group">
              <label for="service">服务类型</label>
              <select id="service" v-model="form.service">
                <option value="">请选择服务类型</option>
                <option value="domestic">国内快递</option>
                <option value="international">国际货运</option>
                <option value="storage">仓储服务</option>
                <option value="cold-chain">冷链物流</option>
                <option value="full-truck">整车运输</option>
                <option value="consulting">物流咨询</option>
              </select>
            </div>
            
            <div class="form-group">
              <label for="message">留言内容 *</label>
              <textarea 
                id="message" 
                v-model="form.message"
                required
                rows="5"
                placeholder="请详细描述您的需求..."
              ></textarea>
            </div>
            
            <button type="submit" class="btn btn-primary submit-btn" :disabled="isSubmitting">
              {{ isSubmitting ? '提交中...' : '立即提交' }}
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const isSubmitting = ref(false)

const form = ref({
  name: '',
  phone: '',
  email: '',
  service: '',
  message: ''
})

const submitForm = async () => {
  isSubmitting.value = true
  
  // 模拟API调用
  setTimeout(() => {
    alert('感谢您的留言！我们会尽快与您联系。')
    // 重置表单
    form.value = {
      name: '',
      phone: '',
      email: '',
      service: '',
      message: ''
    }
    isSubmitting.value = false
  }, 2000)
}
</script>

<style scoped>
.contact {
  padding: 80px 0;
  background: white;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-info h3 {
  color: #333;
  margin-bottom: 1rem;
  font-size: 1.8rem;
}

.contact-info > p {
  color: #666;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.contact-methods {
  display: grid;
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.contact-method {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 10px;
  transition: transform 0.3s;
}

.contact-method:hover {
  transform: translateX(5px);
  background: #e9ecef;
}

.method-icon {
  font-size: 1.5rem;
  flex-shrink: 0;
}

.method-content h4 {
  color: #333;
  margin-bottom: 0.5rem;
}

.method-content p {
  color: #2c5aa0;
  font-weight: 600;
  margin-bottom: 0.25rem;
}

.method-content span {
  color: #666;
  font-size: 0.9rem;
}

.social-links h4 {
  color: #333;
  margin-bottom: 1rem;
}

.social-icons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.social-icon {
  background: #2c5aa0;
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  text-decoration: none;
  transition: all 0.3s;
  font-size: 0.9rem;
}

.social-icon:hover {
  background: #1e3a8a;
  transform: translateY(-2px);
}

.contact-form-container {
  background: #f8f9fa;
  padding: 2.5rem;
  border-radius: 15px;
}

.contact-form h3 {
  color: #333;
  margin-bottom: 2rem;
  text-align: center;
  font-size: 1.5rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  color: #333;
  font-weight: 500;
}

input, select, textarea {
  width: 100%;
  padding: 12px 15px;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s;
  background: white;
}

input:focus, select:focus, textarea:focus {
  outline: none;
  border-color: #2c5aa0;
  box-shadow: 0 0 0 3px rgba(44, 90, 160, 0.1);
}

textarea {
  resize: vertical;
  min-height: 120px;
  font-family: inherit;
}

.submit-btn {
  width: 100%;
  padding: 15px;
  font-size: 1.1rem;
  margin-top: 1rem;
}

.submit-btn:disabled {
  background: #ccc;
  cursor: not-allowed;
  transform: none;
}

/* 平板端响应式 */
@media (max-width: 1024px) {
  .contact-content {
    gap: 3rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
    gap: 0;
  }
}

/* 移动端响应式 */
@media (max-width: 768px) {
  .contact {
    padding: 60px 0;
  }
  
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .contact-form-container {
    padding: 2rem 1.5rem;
  }
  
  .contact-method {
    padding: 1rem;
  }
  
  .social-icons {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .contact-form-container {
    padding: 1.5rem;
  }
  
  .contact-method {
    flex-direction: column;
    text-align: center;
  }
  
  .method-icon {
    align-self: center;
  }
  
  .social-icon {
    padding: 0.5rem 1rem;
    font-size: 0.8rem;
  }
}
</style>