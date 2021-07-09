<template>
  <div>
    <button class="add-button" @click="show = !show">ADD NEW COST  +</button>
    <div v-if="show">
      <input v-model="date" placeholder="date" />
      <input v-model="category" placeholder="category" />
      <input v-model.number="value" type="number" placeholder="value" />
      <button @click="onClick">Add Data</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddPayment",
  data() {
    return {
      date: "",
      category: "",
      value: null,
      show: false
    }
  },
  methods: {
    onClick() {
      const { category, value } = this
      const data = {
        date: this.date || this.getCurrentDate,
        category,
        value
      }
      this.$emit('addNewPayment', data)
    }
  },
  computed: {
    getCurrentDate() {
      const today = new Date()
      const d = today.getDate()
      const m = today.getMonth() + 1
      const y = today.getFullYear()
      return `${d}.${m}.${y}`
    }
  }
}
</script>

<style>
.add-button {
  background: rgb(25, 192, 25);
  border: none;
  color: white;
  height: 30px;
  margin-bottom: 20px;
}
</style>