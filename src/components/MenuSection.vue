<script setup>
import maoxuewang from '../assets/毛血旺.webp'
import shuizhuyu from '../assets/水煮鱼.webp'
import huobaofeichang from '../assets/火爆肥肠.jpg'

const dishes = [
  {
    name: '清蒸太湖白鱼',
    desc: '每日新鲜到店，葱油激香，肉质细嫩如雪，只以少许豉油点睛。',
    price: 128,
    tag: '时令鲜味',
    emoji: '🐟'
  },
  {
    name: '秘制东坡肉',
    desc: '精选五花三层，黄酒冰糖慢煨三小时，色泽红亮，入口即化。',
    price: 88,
    tag: '主厨推荐',
    emoji: '🥩'
  },
  {
    name: '蟹粉狮子头',
    desc: '手工细切三分肥七分瘦，拌入现拆蟹黄，文火清炖至酥嫩。',
    price: 98,
    tag: '手工现做',
    emoji: '🦀'
  },
  {
    name: '龙井虾仁',
    desc: '明前龙井入馔，河虾仁晶莹剔透，茶香清雅，回甘悠长。',
    price: 118,
    tag: '江南雅馔',
    emoji: '🫖'
  },
  {
    name: '山珍佛跳墙',
    desc: '鲍鱼、花胶、瑶柱与山菌同煨，汤醇味厚，一盅藏尽山海。',
    price: 298,
    tag: '限量供应',
    emoji: '🍄'
  },
  {
    name: '桂花糯米藕',
    desc: '糯米填入藕孔，桂花蜜慢煮收汁，清甜软糯，最宜收尾。',
    price: 36,
    tag: '饭后甜点',
    emoji: '🌿'
  },
  {
    name: '毛血旺',
    desc: '鸭血、毛肚与午餐肉同锅翻滚，麻辣鲜烫，一口入魂的川味经典。',
    price: 68,
    tag: '川味经典',
    img: maoxuewang
  },
  {
    name: '水煮鱼',
    desc: '现杀黑鱼片片薄嫩，滚油浇上花椒辣椒，麻辣鲜香瞬间迸发。',
    price: 88,
    tag: '麻辣鲜香',
    img: shuizhuyu
  },
  {
    name: '火爆肥肠',
    desc: '猛火快炒至外焦里嫩，椒香与蒜香交织，脆弹爽口的下饭利器。',
    price: 78,
    tag: '下饭利器',
    img: huobaofeichang
  }
]
</script>

<template>
  <section class="section menu" id="menu">
    <div class="container">
      <div class="section-head">
        <p class="section-eyebrow">SIGNATURE DISHES</p>
        <h2>今日招牌</h2>
        <p class="section-intro">九道经典，尝遍四季风物。</p>
      </div>
      <div class="menu-grid">
        <article v-for="dish in dishes" :key="dish.name" class="dish">
          <div class="dish-art">
            <img v-if="dish.img" :src="dish.img" :alt="dish.name" />
            <span v-else class="emoji">{{ dish.emoji }}</span>
          </div>
          <div class="dish-body">
            <h3>{{ dish.name }}</h3>
            <p>{{ dish.desc }}</p>
            <div class="dish-meta">
              <span class="price"><small>¥</small>{{ dish.price }}</span>
              <span class="tag">{{ dish.tag }}</span>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
