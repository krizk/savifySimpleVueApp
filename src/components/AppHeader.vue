<template>
  <div class="header-box">
      <div class="logo-box">
        <img src="@/assets/logo.png" alt="Savify Logo">
        <div class="logo-text">savify</div>
      </div>
      <div class="header">
        <h1 class="page-title">Overview</h1>

        <div class="view-slider-wrapper med-font">
          <p class="slide-opLft">Budget</p>
          <p class="slide-opRt">Transactions</p>
          <div class="slider-track"></div>
          <div class="slider"></div>
        </div>

        <p class="date sm-font">
          Mar. 2019
          <i class="fas fa-caret-down"></i>
        </p>
      </div>
    </div>
</template>

<script>
export default {
  name: 'app-header',
  props: {
  }
}
</script>

<style scoped>

</style>
