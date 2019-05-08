<template>
    <div class="transaction">
        <i class="fas fa-circle trans-icon"></i>
        <p class="trans-location vsm-font">{{ transaction.description }}</p>
        <p class="trans-amount vsm-font card-right">{{ centsToDollars(transaction.amount) }}</p>
        <p class="trans-date subtext vsm-font">01 Mar 2019</p>
    </div>
</template>

<script>

export default {
  name: 'budget-items',
  props: ['transaction', 'centsToDollars'],

}
</script>

<style scoped>

</style>
