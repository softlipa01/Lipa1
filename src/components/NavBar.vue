<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const scrolled = ref(false)
const open = ref(false)

const onScroll = () => {
  scrolled.value = window.scrollY > 10
}

const toggleMenu = () => {
  open.value = !open.value
}

const closeMenu = () => {
  open.value = false
}

onMounted(() => {
  window.addEventListener('scroll', onScroll, { passive: true })
  onScroll()
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<template>
  <nav class="nav" :class="{ scrolled }">
    <div class="container nav-inner">
      <a href="#top" class="logo">云锦轩<small>YUNJIN XUAN</small></a>
      <ul class="nav-links" :class="{ open }">
        <li><a href="#about" @click="closeMenu">关于我们</a></li>
        <li><a href="#menu" @click="closeMenu">招牌菜</a></li>
        <li><a href="#reviews" @click="closeMenu">食客评价</a></li>
        <li><a href="#reserve" class="nav-cta" @click="closeMenu">在线预订</a></li>
      </ul>
      <button
        class="nav-toggle"
        :aria-expanded="open"
        :aria-label="open ? '关闭菜单' : '打开菜单'"
        @click="toggleMenu"
      >
        <span></span><span></span><span></span>
      </button>
    </div>
  </nav>
</template>
