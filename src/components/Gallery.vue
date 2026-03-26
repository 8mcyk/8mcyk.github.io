<template>
  <section id="gallery" class="gallery">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">服务器画廊</h2>
        <p class="section-subtitle">欣赏我们服务器的精彩瞬间</p>
      </div>
      <div class="gallery-filters">
        <button 
          v-for="filter in filters" 
          :key="filter.id"
          :class="['filter-btn', { active: activeFilter === filter.id }]"
          @click="activeFilter = filter.id"
        >
          {{ filter.name }}
        </button>
      </div>
      <div class="gallery-grid">
        <div 
          v-for="item in filteredGallery" 
          :key="item.id" 
          class="gallery-item"
          @click="openLightbox(item)"
        >
          <img :src="item.image" :alt="item.title" class="gallery-image" />
          <div class="gallery-overlay">
            <div class="overlay-content">
              <h4 class="overlay-title">{{ item.title }}</h4>
              <p class="overlay-desc">{{ item.description }}</p>
              <span class="view-full">点击查看大图</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!--本网站由九条诗织@651715794个人独自完成,未经授权禁止盗用-->
    <div v-if="lightboxOpen" class="lightbox" @click="closeLightbox">
      <div class="lightbox-content" @click.stop>
        <button class="lightbox-close" @click="closeLightbox">&times;</button>
        <img :src="currentLightbox.image" :alt="currentLightbox.title" class="lightbox-image" />
        <div class="lightbox-info">
          <h3>{{ currentLightbox.title }}</h3>
          <p>{{ currentLightbox.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue';

const activeFilter = ref('all');

 const filters = [
/*  { id: 'all', name: '全部' },
  { id: 'survival', name: '生存' },
  { id: 'creative', name: '创造' },
  { id: 'event', name: '活动' } */
];
const galleryItems = [
  {
    id: 1,
    title: '初号机',
    description: '建设者：Kujou_Shiorin',
    image: 'https://free.picui.cn/free/2026/03/03/69a6aa8dc9a54.png',
    category: '#'
  },
  {
    id: 2,
    title: '橘子洲头',
    description: '建设者：8mcyk',
    image: 'https://free.picui.cn/free/2026/02/25/699f1908eb50f.png',
    category: '#'
  },
  {
    id: 3,
    title: '莉莉丝',
    description: '建设者：Kujou_Shiorin',
    image: 'https://free.picui.cn/free/2026/02/25/699f190376d7f.jpg',
    category: '#'
  },
  {
    id: 4,
    title: '铃芽之旅',
    description: '建设者：Kujou_Shiorin / YangYuBushi',
    image: 'https://free.picui.cn/free/2026/02/25/699f190e6bc0b.png',
    category: '#'
  },
  {
    id: 5,
    title: '樱花伞',
    description: '建设者：Kujou_Shiorin',
    image: 'https://free.picui.cn/free/2026/02/25/699f19118e43d.png',
    category: '#'
  },
  {
    id: 6,
    title: '小黑塔',
    description: '建设者：Kujou_Shiorin',
    image: 'https://free.picui.cn/free/2026/02/25/699f190a2c665.png',
    category: '#'
  },
  {
    id: 7,
    title: '拉特兰主机',
    description: '建设者：chengshan0107',
    image: 'https://free.picui.cn/free/2026/02/25/699f190eaa9b7.png',
    category: '#'
  },
  {
    id: 8,
    title: '最高人民法院',
    description: '建设者：sun553595 / Kujou_Shiorin',
    image: 'https://free.picui.cn/free/2026/02/25/699f191106f58.png',
    category: '#'
  },
  {
    id: 9,
    title: '全物品',
    description: '建设者：xiaoyu',
    image: 'https://free.picui.cn/free/2026/03/03/69a6abe1e4bec.png',
    category: '#'
  },
  {
    id: 10,
    title: '月读',
    description: '建设者：Kujou_Shiorin',
    image: 'https://free.picui.cn/free/2026/03/03/69a6acb5d7ea2.png',
    category: '#'
  },
  {
    id: 11,
    title: '東星港',
    description: '建设者：chengshan0107',
    image: 'https://free.picui.cn/free/2026/03/26/69c40c7dc8e51.png',
    category: '#'
  },
  {
    id: 12,
    title: '虚位以待',
    description: 'null',
    image: '虚位以待',
    category: '#'
  }
];

const lightboxOpen = ref(false);
const currentLightbox = ref(galleryItems[0]);

const filteredGallery = computed(() => {
  if (activeFilter.value === 'all') {
    return galleryItems;
  }
  return galleryItems.filter(item => item.category === activeFilter.value);
});

const openLightbox = (item) => {
  currentLightbox.value = item;
  lightboxOpen.value = true;
  document.body.style.overflow = 'hidden';
};

const closeLightbox = () => {
  lightboxOpen.value = false;
  document.body.style.overflow = '';
};
</script>

<style scoped>
.gallery {
  padding: 6rem 2rem;
  background: linear-gradient(180deg, #1a1a2e 0%, #0f172a 100%);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
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

.gallery-filters {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.filter-btn {
  background: rgba(30, 41, 59, 0.8);
  border: 2px solid rgba(74, 222, 128, 0.2);
  color: #94a3b8;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-size: 1rem;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
}

.filter-btn:hover {
  border-color: rgba(74, 222, 128, 0.5);
  color: #4ade80;
}

.filter-btn.active {
  background: linear-gradient(135deg, #4ade80 0%, #22c55e 100%);
  border-color: transparent;
  color: #0f172a;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.gallery-item {
  position: relative;
  border-radius: 16px;
  overflow: hidden;
  cursor: pointer;
  aspect-ratio: 16/9;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.gallery-item:hover {
  transform: scale(1.03);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
}

.gallery-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.gallery-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(to top, rgba(15, 23, 42, 0.95) 0%, rgba(15, 23, 42, 0.3) 50%, transparent 100%);
  opacity: 0;
  transition: opacity 0.4s ease;
  display: flex;
  align-items: flex-end;
  padding: 2rem;
}

.gallery-item:hover .gallery-overlay {
  opacity: 1;
}

.overlay-content {
  transform: translateY(20px);
  transition: transform 0.4s ease;
}

.gallery-item:hover .overlay-content {
  transform: translateY(0);
}

.overlay-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #f1f5f9;
  margin-bottom: 0.5rem;
}

.overlay-desc {
  font-size: 1rem;
  color: #94a3b8;
  margin-bottom: 1rem;
}

.view-full {
  display: inline-block;
  color: #4ade80;
  font-weight: 600;
  font-size: 0.9rem;
}

.lightbox {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.95);
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.lightbox-content {
  position: relative;
  max-width: 1000px;
  width: 100%;
  background: #1e293b;
  border-radius: 16px;
  overflow: hidden;
}

.lightbox-close {
  position: absolute;
  top: 1rem;
  right: 1rem;
  width: 45px;
  height: 45px;
  background: rgba(0, 0, 0, 0.6);
  border: none;
  color: white;
  font-size: 2rem;
  border-radius: 50%;
  cursor: pointer;
  z-index: 10;
  transition: background 0.3s ease;
}

.lightbox-close:hover {
  background: rgba(239, 68, 68, 0.8);
}

.lightbox-image {
  width: 100%;
  max-height: 70vh;
  object-fit: contain;
}

.lightbox-info {
  padding: 2rem;
  text-align: center;
}

.lightbox-info h3 {
  font-size: 1.75rem;
  color: #f1f5f9;
  margin-bottom: 0.5rem;
}

.lightbox-info p {
  font-size: 1.1rem;
  color: #94a3b8;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }
  
  .gallery-grid {
    grid-template-columns: 1fr;
  }
  
  .gallery-overlay {
    opacity: 1;
  }
  
  .overlay-content {
    transform: translateY(0);
  }
}
</style>
