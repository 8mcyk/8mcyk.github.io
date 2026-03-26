<template>
  <footer id="join" class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <h3 class="footer-logo">🟢 Der ewige Schnee</h3>
          <p class="footer-desc">
            一个充满乐趣和友谊的我的世界服务器<br />
            期待你的加入！
          </p>
        </div>
        <div class="footer-section">
          <h4 class="footer-title">快速链接</h4>
          <ul class="footer-links">
            <li><a href="#home">首页</a></li>
            <li><a href="#features">特色</a></li>
            <li><a href="#modes">游戏模式</a></li>
            <li><a href="#rules">规则</a></li>
          </ul>
        </div>
        <div class="footer-section">
          <h4 class="footer-title">联系方式</h4>
          <ul class="footer-links">
            <li><a href="#">📧 邮箱: 2126148479@qq.com</a></li>
            <li><a href="#">💬 QQ群: 768867271</a></li>
            <li><a href="#">🎮 Discord: 没有这种高级の东西</a></li>
          </ul>
        </div>
        <div class="footer-section">
          <h4 class="footer-title">服务器信息</h4>
          <div class="server-ip-box">
            <code>8mcyk.top</code>
            <button class="copy-btn" @click="copyIP">复制</button>
          </div>
          <p class="server-status">
            <span class="status-dot"></span>
            服务器状态: <span class="status-text online">在线</span>
          </p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2026 Der ewige Schnee. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
const copyIP = () => {
  navigator.clipboard.writeText('play.mcserver.com');
  alert('服务器IP已复制到剪贴板！');
};
</script>

<style scoped>
.footer {
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  padding: 4rem 2rem 2rem;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 3rem;
  margin-bottom: 3rem;
}

.footer-section {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.footer-logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: #4ade80;
  margin-bottom: 0.5rem;
}

.footer-desc {
  color: #94a3b8;
  line-height: 1.8;
  font-size: 0.95rem;
}

.footer-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #f1f5f9;
  margin-bottom: 0.5rem;
}

.footer-links {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.footer-links a {
  color: #94a3b8;
  text-decoration: none;
  transition: color 0.3s ease;
  font-size: 0.95rem;
}

.footer-links a:hover {
  color: #4ade80;
}

.server-ip-box {
  display: flex;
  gap: 0.5rem;
  background: rgba(15, 23, 42, 0.8);
  padding: 0.75rem;
  border-radius: 10px;
  border: 1px solid rgba(74, 222, 128, 0.3);
}

.server-ip-box code {
  flex: 1;
  color: #4ade80;
  font-family: 'Courier New', monospace;
  font-size: 1rem;
  display: flex;
  align-items: center;
}

.copy-btn {
  background: linear-gradient(135deg, #4ade80 0%, #22c55e 100%);
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 8px;
  color: #0f172a;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.copy-btn:hover {
  transform: scale(1.05);
  box-shadow: 0 0 15px rgba(74, 222, 128, 0.5);
}

.server-status {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #94a3b8;
  font-size: 0.95rem;
}

.status-dot {
  width: 10px;
  height: 10px;
  background: #4ade80;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

.status-text.online {
  color: #4ade80;
  font-weight: 600;
}

.footer-bottom {
  text-align: center;
  padding-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  color: #64748b;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
  }
}
</style>
