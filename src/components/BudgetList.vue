<template>
    <div id="budgetCards">
        <budget-card
            v-for="(budget, index) in budgetsArr"
            v-bind:key="index"
            v-bind:budget="budget"
        ></budget-card>
    </div>

</template>

<script>
import budgetCard from './BudgetCard.vue'

export default {
  name: 'budget-list',
  components: {
      budgetCard,
  },
  props: ['budgetsArr']
}
</script>

<style scoped>

</style>
