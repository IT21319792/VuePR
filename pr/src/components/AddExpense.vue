<!-- AddExpense.vue -->
<template>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h1>Add Expense</h1>
          <div class="mb-3">
            <input
              name="description"
              type="text"
              class="form-control"
              placeholder="Enter description"
              v-model="description"
            />
          </div>
          <div class="mb-3">
            <input
              name="amount"
              type="number"
              class="form-control"
              placeholder="Enter amount"
              v-model="amount"
            />
          </div>
          <button @click="addExpense" class="btn btn-primary" :disabled="!description || !amount">Add Expense</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        description: '',
        amount: ''
      };
    },
    methods: {
      addExpense() {
        const expense = {
          description: this.description,
          amount: parseFloat(this.amount),
          date: new Date().toLocaleDateString()
        };
        this.$emit('addExpense', expense);
        this.description = '';
        this.amount = '';
        this.$emit('goto', 1);
      }
    }
  };
  </script>
  