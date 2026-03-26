<template>
  <header class="header">
    <div class="container">
      <div class="logo">
        <span class="logo-text">🟢 Der ewige Schnee</span>
      </div>
      <nav class="nav">
        <a href="#home" class="nav-link">首页</a>
        <a href="#features" class="nav-link">特色</a>
        <a href="#modes" class="nav-link">游戏模式</a>
        <a href="#gallery" class="nav-link">画廊</a>
        <a href="#rules" class="nav-link">规则</a>
        <a href="#join" class="nav-link join-btn">立即加入</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
</script>

<style scoped>
.header {
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: bold;
  color: #4ade80;
  text-shadow: 0 0 10px rgba(74, 222, 128, 0.5);
}

.nav {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-link {
  color: #e2e8f0;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: #4ade80;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: #4ade80;
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.join-btn {
  background: linear-gradient(135deg, #4ade80 0%, #22c55e 100%);
  padding: 0.5rem 1.5rem;
  border-radius: 25px;
  color: #0f172a;
}

.join-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 0 20px rgba(74, 222, 128, 0.5);
}

.join-btn::after {
  display: none;
}

@media (max-width: 768px) {
  .nav {
    gap: 1rem;
    font-size: 0.9rem;
  }
  
  .container {
    padding: 0 1rem;
  }
  
  .join-btn {
    padding: 0.4rem 1rem;
  }
}
</style>
