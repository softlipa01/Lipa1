<script setup>
const reviews = [
  {
    text: '带父母来庆生，服务细致周到，东坡肉入口即化，老人赞不绝口。包厢安静雅致，适合家庭聚会。',
    author: '林女士',
    meta: '家庭聚餐 · 2026年7月',
    avatar: '林',
    avatarClass: 'av-1'
  },
  {
    text: '佛跳墙名不虚传，汤底醇厚胶质满满，喝完整个人的疲惫都散了。环境很有江南韵味。',
    author: '陈先生',
    meta: '商务宴请 · 2026年6月',
    avatar: '陈',
    avatarClass: 'av-2'
  },
  {
    text: '第一次来就被龙井虾仁惊艳到，茶香不夺鲜味。桂花糯米藕收尾刚刚好，会再来的。',
    author: '周小姐',
    meta: '朋友小聚 · 2026年7月',
    avatar: '周',
    avatarClass: 'av-3'
  }
]
</script>

<template>
  <section class="section quotes" id="reviews">
    <div class="container">
      <div class="section-head">
        <p class="section-eyebrow">GUEST REVIEWS</p>
        <h2>食客心声</h2>
        <p class="section-intro">来自真实客人的每一句评价，都是我们前行的底气。</p>
      </div>
      <div class="quotes-grid">
        <blockquote v-for="review in reviews" :key="review.author" class="quote">
          <div class="stars">★★★★★</div>
          <p>{{ review.text }}</p>
          <div class="quote-author">
            <div class="avatar" :class="review.avatarClass">{{ review.avatar }}</div>
            <div><b>{{ review.author }}</b><span>{{ review.meta }}</span></div>
          </div>
        </blockquote>
      </div>
    </div>
  </section>
</template>
