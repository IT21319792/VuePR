<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <h1>Expense Summary</h1>
        <div class="mb-3">
          <h6>Total Expenses: LKR {{ totalExpenses.toFixed(2) }}</h6>
        </div>
        <div class="mb-3">
          <h4>Expense Report</h4>
          <table class="table table-bordered">
            <thead>
              <tr>
                <th>Date</th>
                <th>Description</th>
                <th>Amount</th>

              </tr>
            </thead>
            <tbody>
              <tr v-for="expense in expenses" :key="expense.date + expense.description">
                <td>{{ expense.date }}</td>
                <td>{{ expense.description }}</td>
                <td>LKR {{ expense.amount.toFixed(2) }}</td>

              </tr>
              <tr>
                <div class="mb-3">
                  <h6>Total Expenses: LKR {{ totalExpenses.toFixed(2) }}</h6>
                </div>
              </tr>
            </tbody>
          </table>
        </div>
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

<style scoped>
.table {
  margin-top: 20px;
}
</style>
