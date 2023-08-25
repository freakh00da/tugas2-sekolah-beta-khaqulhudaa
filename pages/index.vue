<template>
  <div>
    <AppHeader />
    <h1>Welcome to Tugas Sekolah Beta NuxtJs</h1>
    <p>This should be HomePage.</p>
    <FooterMenu />
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import FooterMenu from '@/components/FooterMenu.vue'

export default {
  components: {
    AppHeader,
    FooterMenu,
  },
}
</script>

<style>
h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

p {
  font-size: 1.2rem;
  color: #666;
}
</style>
