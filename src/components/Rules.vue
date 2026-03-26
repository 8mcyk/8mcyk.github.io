<template>
  <section id="rules" class="rules">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">服务器规则</h2>
        <p class="section-subtitle">共同维护良好的游戏环境</p>
      </div>
      <div class="rules-content">
        <div class="rules-list">
          <div v-for="(rule, index) in rules" :key="index" class="rule-item">
            <div class="rule-number">{{ index + 1 }}</div>
            <div class="rule-text">
              <h4 class="rule-title">{{ rule.title }}</h4>
              <p class="rule-desc">{{ rule.description }}</p>
            </div>
          </div>
        </div>
        <div class="rules-notice">
          <div class="notice-card">
            <div class="notice-icon">⚠️</div>
            <div class="notice-content">
              <h3>违规处罚</h3>
              <p>违反规则将根据情节严重程度给予警告、禁言、临时封禁或永久封禁处罚。</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<!--本网站由九条诗织@651715794个人独自完成,未经授权禁止盗用-->
<script setup>
const rules = [
  {
    title: '禁止外挂作弊',
    description: '严禁透视、飞行、自动挖矿等违规模组'
  },
  {
    title: '禁止熊家破坏',
    description: '未经允许不得拆毁、改动他人建筑'
  },
  {
    title: '禁止偷窃物品',
    description: '不许私自拿取他人箱子、容器内物资'
  },
  {
    title: '文明友好交流',
    description: '不辱骂、不刷屏、不发布违规内容'
  },
  {
    title: '禁止恶意 PVP',
    description: '我们提供完善的领地保护机制，个人恩怨请前往野外解决'
  },
  {
    title: '服从管理裁决',
    description: '尊重管理员判定，违规将按规处罚'
  }
];
</script>

<style scoped>
.rules {
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #0f172a 0%, #1a1a2e 100%);
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

.rules-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 3rem;
  align-items: start;
}

.rules-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.rule-item {
  display: flex;
  gap: 1.5rem;
  background: rgba(30, 41, 59, 0.6);
  padding: 2rem;
  border-radius: 16px;
  border-left: 4px solid #4ade80;
  transition: all 0.3s ease;
}

.rule-item:hover {
  transform: translateX(10px);
  background: rgba(30, 41, 59, 0.9);
}

.rule-number {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #4ade80 0%, #22c55e 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 700;
  color: #0f172a;
  flex-shrink: 0;
}

.rule-text {
  flex: 1;
}

.rule-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #f1f5f9;
  margin-bottom: 0.5rem;
}

.rule-desc {
  font-size: 1rem;
  color: #94a3b8;
  line-height: 1.7;
}

.rules-notice {
  position: sticky;
  top: 100px;
}

.notice-card {
  background: linear-gradient(135deg, rgba(239, 68, 68, 0.2) 0%, rgba(248, 113, 113, 0.1) 100%);
  border: 2px solid rgba(239, 68, 68, 0.4);
  border-radius: 20px;
  padding: 2rem;
  text-align: center;
}

.notice-icon {
  font-size: 4rem;
  margin-bottom: 1rem;
}

.notice-content h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #fca5a5;
  margin-bottom: 1rem;
}

.notice-content p {
  font-size: 1rem;
  color: #fecaca;
  line-height: 1.7;
}

@media (max-width: 968px) {
  .rules-content {
    grid-template-columns: 1fr;
  }
  
  .rules-notice {
    position: static;
  }
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }
  
  .rule-item {
    flex-direction: column;
    gap: 1rem;
  }
}
</style>
