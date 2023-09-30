<template>
  <div>
    <AppHeader />
    <h1>Daftar Artikel</h1>
    <div class="article-list">
      <div v-for="article in articles" :key="article.id" class="article-card">
        <img :src="article.img" alt="Gambar Artikel" />
        <h2>{{ article.title }}</h2>
        <p>{{ article.content }}</p>
        <nuxt-link :to="'/article/' + article.id">Baca Selengkapnya</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import articles from '~/assets/articles.js'
import AppHeaderVue from '~/components/AppHeader.vue'

export default {
  components: AppHeaderVue,
  data() {
    return {
      articles,
    }
  },
}
</script>

<style scoped>
.article-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.article-card {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  width: calc(20% - 20px);
}

.article-card img {
  max-width: 100%;
  height: auto;
}

.article-card h2 {
  font-size: 1.5rem;
  font-weight: bold;
  margin: 10px 0;
}

.article-card p {
  font-size: 1rem;
  color: #333;
  margin-bottom: 10px;
}
</style>
