<template>
  <div>
    <AppHeader />
    <h1>Contact Us</h1>
    <p>This is the Contact Us page.</p>
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
