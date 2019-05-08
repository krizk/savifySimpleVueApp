<template>

    <div class="cat-card" @click="hidden = !hidden">

      <div class="card-icon">
        <img :src="imgPath" alt="icon">
      </div>

      <div class="card-content">
        <p class="card-title">{{ budget.name }}</p>
        <p class="sm-font card-right budget-dollar-text">
          {{centsToDollars(transactionTotal(budget.transactions))}} /
          <span
            class="highlight-text"
          >{{ centsToDollars(budget.target) }}</span>
        </p>
        <p class="subtext vsm-font">{{ budget.transactions.length }} transactions</p>
        <p
          class="subtext vsm-font card-right"
        >{{percentBudget(transactionTotal(budget.transactions), budget.target)}} of budget</p>
        <div class="budget-bar">
          <div class="total-bar"></div>
          <div
            :style="{ width: budgetBarWidth(transactionTotal(budget.transactions), budget.target) }"
            class="used-bar"
          ></div>
        </div>
      </div>
      <div class="transaction-card">
              <budget-items
          :class="{ hidden: hidden }"
          v-for="(transaction, index) in budget.transactions"
          v-bind:key="index"
          v-bind:transaction="transaction"
          v-bind:centsToDollars="centsToDollars"
      ></budget-items>
      </div>
    </div>

</template>

<script>
import budgetItems from './BudgetItems.vue'

export default {
  name: 'budget-card',
  props: ['budget'],
  components: {
    budgetItems
  },
  data() {
    return {
      hidden: true
    }
  },
  computed: {
    imgPath () {
      if (this.budget) {
        return `${this.budget.name.toLowerCase()}.png`
      } else {
        return "image not found"
      }
    }
  },
  methods: {
    transactionTotal(transactions) {
      let total = 0;
      transactions.forEach(transaction => {
        total += transaction.amount;
      });
      return total;
    },
    centsToDollars(cents) {
      let dollars = cents / 100;
      let formatedDollars = dollars.toLocaleString("en-US", {
        style: "currency",
        currency: "USD"
      });
      return formatedDollars;
    },
    percentBudget(spent, budget) {
      return `${Math.round((spent / budget) * 100)}%`;
    },
    budgetBarWidth(spent, budget) {
      if (budget > spent) {
        return `${Math.round((spent / budget) * 100)}%`;
      } else {
        return "100%";
      }
    }
  }
}
</script>

<style scoped>

</style>