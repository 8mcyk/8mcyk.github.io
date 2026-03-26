<template>
  <section id="home" class="hero">
    <div class="hero-background">
      <div class="hero-bg-image"></div>
      <div class="hero-bg-overlay"></div>
    </div>
    <div class="hero-content">
      <div class="hero-badge">✨ 2026 全新版本</div>
      <h1 class="hero-title">欢迎来到<br /><span class="highlight">Der ewige Schnee 服务器</span></h1>
      <p class="hero-description">
        探索无限可能，结交志同道合的伙伴<br />
        生存、创造、冒险，尽在其中
      </p>
      <div class="server-info">
        <div class="info-card">
          <div class="info-icon">👥</div>
          <div class="info-text">
            <div class="info-number">{{ onlinePlayers }}</div>
            <div class="info-label">在线玩家</div>
          </div>
        </div>
        <div class="info-card">
          <div class="info-icon">🌍</div>
          <div class="info-text">
            <div class="info-number">1.21.11</div>
            <div class="info-label">服务器版本</div>
          </div>
        </div>
        <div class="info-card">
          <div class="info-icon">⚡</div>
          <div class="info-text">
            <div class="info-number">20</div>
            <div class="info-label">平均延迟</div>
          </div>
        </div>
      </div>
      <div class="hero-actions">
        <button class="btn btn-primary" @click="copyIP">
          📋 复制服务器IP
        </button>
        <button class="btn btn-secondary" @click="openStream">
          📺 查看直播
        </button>
      </div>
      <div class="ip-display" :class="{ copied: isCopied }">
        <code>{{ serverIP }}</code>
        <span v-if="isCopied" class="copied-text">已复制!</span>
      </div>
    </div>
    <div class="hero-decoration">
      <div class="cube cube-1"></div>
      <div class="cube cube-2"></div>
      <div class="cube cube-3"></div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const onlinePlayers = ref(128);
const serverIP = ref('8mcyk.top');
const isCopied = ref(false);

const copyIP = () => {
  navigator.clipboard.writeText(serverIP.value);
  isCopied.value = true;
  setTimeout(() => {
    isCopied.value = false;
  }, 2000);
};

const openStream = () => {
  window.open('https://live.douyin.com/531562885254', '_blank');
};
</script>

<style scoped>
.hero {
  min-height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  padding: 2rem;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
}

.hero-bg-image {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url('https://free.picui.cn/free/2026/03/16/69b7c72cc2756.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  animation: subtleZoom 30s ease-in-out infinite;
}

.hero-bg-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    to bottom,
    rgba(15, 23, 42, 0.7) 0%,
    rgba(15, 23, 42, 0.85) 50%,
    rgba(15, 23, 42, 0.95) 100%
  );
}

@keyframes subtleZoom {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

.hero-content {
  max-width: 900px;
  text-align: center;
  z-index: 10;
}

.hero-badge {
  display: inline-block;
  background: rgba(74, 222, 128, 0.1);
  border: 1px solid rgba(74, 222, 128, 0.3);
  padding: 0.5rem 1.5rem;
  border-radius: 50px;
  color: #4ade80;
  font-size: 0.9rem;
  margin-bottom: 1.5rem;
}

.hero-title {
  font-size: 4rem;
  font-weight: 800;
  color: #f1f5f9;
  line-height: 1.2;
  margin-bottom: 1rem;
}

.highlight {
  background: linear-gradient(135deg, #4ade80 0%, #22d3ee 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-description {
  font-size: 1.25rem;
  color: #94a3b8;
  margin-bottom: 2.5rem;
  line-height: 1.8;
}

.server-info {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 2.5rem;
  flex-wrap: wrap;
}

.info-card {
  background: rgba(30, 41, 59, 0.8);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(74, 222, 128, 0.2);
  border-radius: 16px;
  padding: 1.5rem 2rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  min-width: 180px;
}

.info-icon {
  font-size: 2.5rem;
}

.info-text {
  text-align: left;
}

.info-number {
  font-size: 1.75rem;
  font-weight: 700;
  color: #4ade80;
}

.info-label {
  font-size: 0.9rem;
  color: #94a3b8;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 12px;
  font-size: 1.1rem;
  font-weight: 600;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-primary {
  background: linear-gradient(135deg, #4ade80 0%, #22c55e 100%);
  color: #0f172a;
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(74, 222, 128, 0.4);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: #f1f5f9;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-3px);
}

.ip-display {
  display: inline-flex;
  align-items: center;
  gap: 1rem;
  background: rgba(15, 23, 42, 0.8);
  padding: 1rem 2rem;
  border-radius: 12px;
  border: 1px solid rgba(74, 222, 128, 0.3);
}

.ip-display.copied {
  border-color: #4ade80;
  box-shadow: 0 0 20px rgba(74, 222, 128, 0.5);
}

.ip-display code {
  font-size: 1.25rem;
  color: #4ade80;
  font-family: 'Courier New', monospace;
}

.copied-text {
  color: #4ade80;
  font-weight: 600;
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.hero-decoration {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  overflow: hidden;
  pointer-events: none;
}

.cube {
  position: absolute;
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, rgba(74, 222, 128, 0.2) 0%, rgba(34, 211, 238, 0.2) 100%);
  border: 1px solid rgba(74, 222, 128, 0.3);
  animation: float 6s ease-in-out infinite;
}

.cube-1 {
  top: 20%;
  left: 10%;
  animation-delay: 0s;
}

.cube-2 {
  top: 60%;
  right: 15%;
  animation-delay: 2s;
}

.cube-3 {
  bottom: 20%;
  left: 20%;
  animation-delay: 4s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0) rotate(0deg);
  }
  50% {
    transform: translateY(-30px) rotate(180deg);
  }
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-description {
    font-size: 1rem;
  }
  
  .info-card {
    min-width: 140px;
    padding: 1rem 1.5rem;
  }
  
  .info-number {
    font-size: 1.5rem;
  }
}
</style>
