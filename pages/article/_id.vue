<template>
  <div>
    <div class="article-card">
      <div class="article-image">
        <img :src="article.img" alt="Article Image" />
      </div>
      <div class="article-content">
        <h1>{{ article.title }}</h1>
        <p>{{ article.content }}</p>
      </div>
    </div>
    <nuxt-link to="/articles">
      <h2>go back</h2>
    </nuxt-link>
  </div>
</template>

<script>
import articles from '~/assets/articles'

export default {
  computed: {
    article() {
      const id = parseInt(this.$route.params.id)
      return articles.find((article) => article.id === id) || {}
    },
  },
}
</script>

<style scoped>
.article-card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  overflow: hidden;
  margin: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  display: flex;
  flex-direction: column;
  width: 40%;
}

.article-image img {
  width: 100%;
  height: auto;
}

.article-content {
  padding: 20px;
}

.article-content h1 {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 10px;
}

.article-content p {
  font-size: 1rem;
  color: #333;
}
</style>
