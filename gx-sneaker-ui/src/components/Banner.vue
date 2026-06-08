<template>
  <section class="hero">
    <img
      :src="banners[current]"
      alt="Banner GX Sneaker"
      class="banner-image"
    >

    ```
    <div class="slider-dots">
  <span
    v-for="(banner, index) in banners"
    :key="index"
    class="dot"
    :class="{ active: current === index }"
  ></span>
    </div>
    ```

  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

import banner1 from '@/assets/images/banner1.png'
import banner2 from '@/assets/images/banner2.png'

const current = ref(0)

const banners = [
  banner1,
  banner2
]

onMounted(() => {
  setInterval(() => {
    current.value = (current.value + 1) % banners.length
  }, 3000)
})
</script>

<style scoped>
.banner-image {
  width: 100%;
  display: block;
}
</style>
