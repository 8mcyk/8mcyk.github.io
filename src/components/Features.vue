<template>
  <section id="features" class="features">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">服务器特色</h2>
        <p class="section-subtitle">我们精心制作了多个原创数据包，为玩家提供独特的游戏体验</p>
      </div>
      <div class="features-grid">
        <div v-for="feature in features" :key="feature.id" class="feature-card">
          <div class="feature-icon">{{ feature.icon }}</div>
          <h3 class="feature-title">{{ feature.title }}</h3>
          <p class="feature-description">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
<!--本网站由九条诗织@651715794个人独自完成,未经授权禁止盗用-->
<script setup>
const features = [
  {
    id: 1,
    icon: '🎮',
    title: '生存模式',
    description: '经典生存体验，与好友一起探索、建造、战斗，享受纯粹的Minecraft乐趣'
  },
  {
    id: 2,
    icon: '🔧',
    title: '原创玩法',
    description: '我们精心制作了多个原创数据包，为玩家提供独特的游戏体验'
  },
  {
    id: 3,
    icon: '💾',
    title: '奇观建设',
    description: '我们鼓励玩家在服务器中建造宏伟的建筑和奇观，展现创造力'
  },
  {
    id: 4,
    icon: '👥',
    title: '活跃社区',
    description: '参与各种社区活动，与其他玩家互动，共同建设繁荣的服务器环境'
  },
  {
    id: 5,
    icon: '🛡️',
    title: '领地保护',
    description: '我们提供完善的领地保护机制，确保玩家的建筑和资源安全'
  },
  {
    id: 6,
    icon: '🌐',
    title: '高性能服务器',
    description: '我们提供稳定、流畅的游戏体验，确保每一位玩家都能享受到最佳的性能表现'
  }
];
</script>

<style scoped>
.features {
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #0f172a 0%, #1e293b 100%);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 3rem;
  font-weight: 800;
  color: #f1f5f9;
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.25rem;
  color: #94a3b8;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: rgba(30, 41, 59, 0.6);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(74, 222, 128, 0.1);
  border-radius: 20px;
  padding: 2.5rem;
  text-align: center;
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.feature-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #4ade80, #22d3ee);
  transform: scaleX(0);
  transition: transform 0.4s ease;
}

.feature-card:hover {
  transform: translateY(-10px);
  border-color: rgba(74, 222, 128, 0.4);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}

.feature-card:hover::before {
  transform: scaleX(1);
}

.feature-icon {
  font-size: 4rem;
  margin-bottom: 1.5rem;
  display: inline-block;
  transition: transform 0.4s ease;
}

.feature-card:hover .feature-icon {
  transform: scale(1.2) rotate(10deg);
}

.feature-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #f1f5f9;
  margin-bottom: 1rem;
}

.feature-description {
  font-size: 1rem;
  color: #94a3b8;
  line-height: 1.8;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
  }
}
</style>
