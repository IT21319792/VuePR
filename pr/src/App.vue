<template>
  <div class="container">
    <component
      :is="screens[position]"
      :expenses="expenses"
      @goto="handleGoTo"
      @addExpense="handleAddExpense"
    />
  </div>
</template>

<script>
import AddExpense from './components/AddExpense.vue';
import ViewExpenses from './components/ViewExpenses.vue';
import Summary from './components/SummaryRep.vue';

export default {
  components: {
    AddExpense,
    ViewExpenses,
    Summary
  },
  data() {
    return {
      screens: ['AddExpense', 'ViewExpenses', 'Summary'],
      position: 0,
      expenses: []
    };
  },
  methods: {
    handleGoTo(position) {
      this.position = position;
    },
    handleAddExpense(expense) {
      this.expenses.push(expense);
      this.position = 1; // Go to ViewExpenses after adding an expense
    }
  }
};
</script>

<style>
  @import './assets/style.css';
</style>
