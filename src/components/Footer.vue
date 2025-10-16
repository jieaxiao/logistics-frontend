// 响应式页脚
<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <div class="footer-logo">
            <h3>速达物流</h3>
            <p>专业物流解决方案提供商</p>
          </div>
          <div class="footer-contact">
            <p>📞 400-123-4567</p>
            <p>✉️ info@express.com</p>
            <p>📍 北京市朝阳区物流园区88号</p>
          </div>
          <div class="footer-social">
            <a href="#" class="social-link">微信</a>
            <a href="#" class="social-link">微博</a>
            <a href="#" class="social-link">抖音</a>
          </div>
        </div>
        
        <div class="footer-section">
          <h4>快速链接</h4>
          <ul class="footer-links">
            <li><a href="#home">首页</a></li>
            <li><a href="#services">服务项目</a></li>
            <li><a href="#tracking">物流追踪</a></li>
            <li><a href="#about">关于我们</a></li>
            <li><a href="#contact">联系我们</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>服务项目</h4>
          <ul class="footer-links">
            <li><a href="#">国内快递</a></li>
            <li><a href="#">国际货运</a></li>
            <li><a href="#">仓储服务</a></li>
            <li><a href="#">冷链物流</a></li>
            <li><a href="#">整车运输</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>客户服务</h4>
          <ul class="footer-links">
            <li><a href="#">帮助中心</a></li>
            <li><a href="#">常见问题</a></li>
            <li><a href="#">服务条款</a></li>
            <li><a href="#">隐私政策</a></li>
            <li><a href="#">投诉建议</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>微信公众号</h4>
          <div class="wechat-qr">
            <div class="qr-placeholder">
              <span>微信公众号二维码</span>
            </div>
            <p>扫码关注最新动态</p>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <div class="footer-bottom-content">
          <p>&copy; 2024 速达物流 版权所有 ICP备案号：京ICP备12345678号</p>
          <div class="footer-certificates">
            <span>诚信企业</span>
            <span>质量认证</span>
            <span>安全运输</span>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
// 页脚逻辑
</script>

<style scoped>
.footer {
  background: #2c3e50;
  color: white;
  padding: 3rem 0 1rem;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr 1fr;
  gap: 2rem;
  margin-bottom: 2rem;
}

.footer-section h3,
.footer-section h4 {
  margin-bottom: 1rem;
  color: #ff6b35;
}

.footer-logo h3 {
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
}

.footer-logo p {
  color: #bdc3c7;
  margin-bottom: 1.5rem;
}

.footer-contact p {
  margin: 0.5rem 0;
  color: #bdc3c7;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.footer-social {
  display: flex;
  gap: 1rem;
  margin-top: 1.5rem;
}

.social-link {
  background: rgba(255, 255, 255, 0.1);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  text-decoration: none;
  font-size: 0.9rem;
  transition: background 0.3s;
}

.social-link:hover {
  background: rgba(255, 255, 255, 0.2);
}

.footer-links {
  list-style: none;
  padding: 0;
}

.footer-links li {
  margin-bottom: 0.75rem;
}

.footer-links a {
  color: #bdc3c7;
  text-decoration: none;
  transition: color 0.3s;
  font-size: 0.9rem;
}

.footer-links a:hover {
  color: white;
}

.wechat-qr {
  text-align: center;
}

.qr-placeholder {
  width: 120px;
  height: 120px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  color: #bdc3c7;
  font-size: 0.8rem;
  text-align: center;
  padding: 0.5rem;
}

.wechat-qr p {
  color: #bdc3c7;
  font-size: 0.9rem;
  margin: 0;
}

.footer-bottom {
  border-top: 1px solid #34495e;
  padding-top: 2rem;
}

.footer-bottom-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-bottom p {
  color: #bdc3c7;
  margin: 0;
  font-size: 0.9rem;
}

.footer-certificates {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.footer-certificates span {
  background: rgba(255, 255, 255, 0.1);
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.8rem;
  color: #bdc3c7;
}

/* 平板端响应式 */
@media (max-width: 1024px) {
  .footer-content {
    grid-template-columns: 1fr 1fr 1fr;
    gap: 2rem;
  }
}

/* 移动端响应式 */
@media (max-width: 768px) {
  .footer {
    padding: 2rem 0 1rem;
  }
  
  .footer-content {
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }
  
  .footer-bottom-content {
    flex-direction: column;
    text-align: center;
  }
  
  .footer-certificates {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 1.5rem;
    text-align: center;
  }
  
  .footer-social {
    justify-content: center;
  }
  
  .footer-contact p {
    justify-content: center;
  }
  
  .qr-placeholder {
    width: 100px;
    height: 100px;
  }
}
</style>