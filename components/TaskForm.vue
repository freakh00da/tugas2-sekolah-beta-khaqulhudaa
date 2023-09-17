<template>
  <div class="task-form">
    <form @submit.prevent="addItem">
      <div class="form-group">
        <label for="item">Item:</label>
        <input id="item" v-model="newItem" type="text" />
      </div>
      <div class="form-group">
        <label for="category">Category:</label>
        <select id="category" v-model="newCategory">
          <option value="Angka">Angka</option>
          <option value="Huruf">Huruf</option>
        </select>
      </div>
      <button type="submit">Add Item</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newItem: '',
      newCategory: '',
    }
  },
  methods: {
    addItem() {
      if (this.newItem.trim() === '' || this.newCategory.trim() === '') {
        alert('Kolom "Item" dan "Category" harus diisi.')
        return
      }
      this.$emit('item-added', {
        title: this.newItem,
        category: this.newCategory,
      })
      this.newItem = ''
      this.newCategory = ''
    },
  },
}
</script>

<style scoped>
.task-form {
  text-align: left;
}

.form-group {
  margin-bottom: 1rem;
}

label {
  font-weight: bold;
  margin-right: 0.5rem;
}

input,
select {
  padding: 0.5rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-right: 1rem;
}

button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
