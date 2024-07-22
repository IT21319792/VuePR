<!-- Summary.vue -->
<template>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h1>Expense Summary</h1>
          <p>Total Expenses: ${{ totalExpenses.toFixed(2) }}</p>
          <button @click="gotoAddExpense" class="btn btn-primary mt-3">Add More</button>
          <button @click="gotoViewExpenses" class="btn btn-secondary mt-3">View All Expenses</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['expenses'],
    computed: {
      totalExpenses() {
        return this.expenses.reduce((total, expense) => total + expense.amount, 0);
      }
    },
    methods: {
      gotoAddExpense() {
        this.$emit('goto', 0);
      },
      gotoViewExpenses() {
        this.$emit('goto', 1);
      }
    }
  };
  </script>
  