<template>
  <div>
    <AppHeader />
    <h1>Welcome to Tugas Sekolah Beta NuxtJs</h1>
    <p>This should be HomePage.</p>
    <div>
      <label for="category">Filter by Category:</label>
      <select id="category" v-model="selectedCategory">
        <option value="Semua">Semua</option>
        <option value="Angka">Angka</option>
        <option value="Huruf">Huruf</option>
      </select>
    </div>
    <ul>
      <li v-for="task in filteredTasks" :key="task.id">{{ task.title }}</li>
    </ul>
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
  data() {
    return {
      tasks: [
        { id: 1, title: '1', category: 'Angka' },
        { id: 2, title: '2', category: 'Angka' },
        { id: 3, title: '3', category: 'Angka' },
        { id: 4, title: 'Satu', category: 'Huruf' },
        { id: 5, title: 'Dua', category: 'Huruf' },
        { id: 6, title: 'Tiga', category: 'Huruf' },
      ],
      selectedCategory: 'Semua',
    }
  },
  computed: {
    filteredTasks() {
      if (this.selectedCategory === 'Semua') {
        return this.tasks
      } else {
        return this.tasks.filter(
          (task) => task.category === this.selectedCategory
        )
      }
    },
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

label {
  font-weight: bold;
  margin-right: 0.5rem;
}

select {
  padding: 0.5rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
