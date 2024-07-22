<!-- ViewExpenses.vue -->
<template>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h1>View Expenses</h1>
          <ul class="list-group">
            <li class="list-group-item" v-for="expense in expenses" :key="expense.date + expense.description">
              {{ expense.date }} - {{ expense.description }}: ${{ expense.amount.toFixed(2) }}
            </li>
          </ul>
          <button @click="gotoSummary" class="btn btn-primary mt-3">Summary</button>
          <button @click="gotoAddExpense" class="btn btn-secondary mt-3">Add More</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['expenses'],
    methods: {
      gotoSummary() {
        this.$emit('goto', 2);
      },
      gotoAddExpense() {
        this.$emit('goto', 0);
      }
    }
  };
  </script>
  