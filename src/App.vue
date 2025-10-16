<template>
  <div id="app">
    <LogisticsHome />
  </div>
</template>

<script setup>
import LogisticsHome from './views/LogisticsHome.vue'
</script>

<style>
/* 全局重置样式 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Arial', 'Microsoft YaHei', sans-serif;
  line-height: 1.6;
  color: #333;
  overflow-x: hidden;
}

/* 响应式容器 */
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* 响应式图片 */
img {
  max-width: 100%;
  height: auto;
}

/* 通用按钮样式 */
.btn {
  display: inline-block;
  padding: 12px 30px;
  border: none;
  border-radius: 5px;
  text-decoration: none;
  font-weight: 600;
  text-align: center;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 16px;
}

.btn-primary {
  background: #ff6b35;
  color: white;
}

.btn-primary:hover {
  background: #e55a2b;
  transform: translateY(-2px);
}

.btn-secondary {
  background: transparent;
  color: #2c5aa0;
  border: 2px solid #2c5aa0;
}

.btn-secondary:hover {
  background: #2c5aa0;
  color: white;
}

/* 响应式工具类 */
.text-center {
  text-align: center;
}

.mobile-only {
  display: none;
}

.desktop-only {
  display: block;
}

/* 移动端优化 */
@media (max-width: 768px) {
  .mobile-only {
    display: block;
  }
  
  .desktop-only {
    display: none;
  }
  
  .btn {
    padding: 14px 25px;
    width: 100%;
    font-size: 16px;
  }
}
</style>