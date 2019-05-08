<template>
  <div class="site-container">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">

    <app-header></app-header>

    <budget-list
      v-bind:budgetsArr="budgets"
    ></budget-list>
    
    <app-footer></app-footer>

    
  </div>
</template>

<script>
import appHeader from './components/AppHeader.vue'
import budgetList from './components/BudgetList.vue'
import appFooter from './components/AppFooter.vue'

export default {
  name: "app",
  components: {
    appHeader,
    budgetList,
    appFooter
  },
  data: () => {
    return {
      budgets: [
        {
          name: "Groceries",
          target: "80000",
          transactions: [
            {
              description:
                "APPLE PAY - SENT M 01-31 877-233-8552 CA 1269 DEBIT CARD PURCHASE",
              amount: 2031
            },
            {
              description:
                "APPLE PAY - SENT M 01-31 877-233-8552 CA 1269 DEBIT CARD PURCHASE",
              amount: 12781
            },
            {
              description: "WEGMANS CHARLOTTES #127",
              amount: 4528
            },
            {
              description: "TRADER JOE'S #661 QPS",
              amount: 2042
            }
          ]
        },
        {
          name: "Rent",
          target: "200000",
          transactions: [
            {
              description: "Check # 1221",
              amount: 20000
            }
          ]
        },
        {
          name: "Utilities",
          target: "30000",
          transactions: [
            {
              description: "ONLINE PMT DOMINION VA POWE 5NEG ACH DEBIT",
              amount: 14700
            },
            {
              description: "COMCAST",
              amount: 7700
            },
            {
              description: "CITY OF CHARLOTTESVILLE",
              amount: 17622
            }
          ]
        },
        {
          name: "Healthcare",
          target: "30000",
          transactions: [
            {
              description: "CVS/PHARMACY #01551",
              amount: 319
            },
            {
              description: "UVA HS MY CHART",
              amount: 20244
            }
          ]
        },
        {
          name: "Entertainment",
          target: "20000",
          transactions: [
            {
              description:
                "Netflix.com 02-26 netflix.com CA 3284 DEBIT CARD RECURRING PYMT",
              amount: 1099
            },
            {
              description: "Regal Cinema 8810-2 EMIT ST PURCHASE",
              amount: 1099
            },
            {
              description: "TIN WHISTLE IRISH PUB 001-22 HIGH ST - PURCHASE",
              amount: 4517
            },
            {
              description: "GUADALAJARA MEXICAN REST",
              amount: 5000
            }
          ]
        }
      ]
    }
  },
  methods: {
    
  }
};
</script>

<style>
*,
*:before,
*:after {
  box-sizing: inherit;
  margin: 0;
  padding: 0;
}

html {
  height: 100%;
}

body {
  background-color: #f8f9fb;
  min-height: 100%;
}

.site-container {
  font-family: sans-serif;
  color: #323b65;
  height: 100%;
  /* display: grid;
    grid-template-rows: auto auto auto; */
  display: flex;
  min-height: 100vh;
  flex-direction: column;
  justify-content: space-between;
}

.site-container > * {
  padding: 15px;
}

.header-box,
.footer {
  background-image: linear-gradient(-180deg, #8e2de2 0%, #4a00e0 100%);
  color: white;
  padding-bottom: 5px;
}

.vsm-font {
  font-size: 0.65rem;
}
.sm-font {
  font-size: 0.7rem;
}
.med-font {
  font-size: 0.8rem;
}

.highlight-text {
  color: #8e2de2;
}

.header {
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: 1fr;
  justify-items: center;
  grid-row-gap: 15px;
}

.logo-box {
  display: flex;
  align-items: center;
  justify-self: left;
  margin-bottom: 5px;
}

.logo-text {
  margin-left: 0.25rem;
  font-weight: bold;
  display: inline-block;
}

.page-title {
  font-size: 1.25rem;
  font-weight: normal;
}

/* SLIDER STYLES */
.view-slider-wrapper {
  display: grid;
  width: fit-content;
  grid-template-rows: 23px;
  grid-template-columns: 110px 110px;
}

.view-slider-wrapper > * {
  grid-row: 1 / -1;
  grid-column: 1 / -1;
}

.view-slider-wrapper > p {
  z-index: 2;
  align-self: center;
  justify-self: center;
}

.slide-opLft {
  grid-column: 1 / 2;
  color: #4a00e0;
}

.slide-opRt {
  color: white;
  grid-column: 2 / -1;
}

.slider-track {
  background: rgba(255, 255, 255, 0.25);
  opacity: 100%;
  border-radius: 14px;
}

.slider {
  background-color: white;
  z-index: 1;
  grid-column: 1 / 2;
  border-radius: 14px;
  -webkit-box-shadow: 10px 5px 15px -13px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 10px 5px 15px -13px rgba(0, 0, 0, 0.75);
  box-shadow: 10px 5px 15px -13px rgba(0, 0, 0, 0.75);
}
/* END SLIDER STYLES */

.date i {
  margin-left: 0.85rem;
}

/*  CARD STYLES */

.cat-card {
  background-color: #ffffff;
  padding: 1rem;
  border-radius: 5px;
  display: grid;
  grid-template-rows: 1fr auto;
  grid-row-gap: 20px;
  grid-template-columns: 1fr 5fr;
  margin-bottom: 10px;
}

.card-icon {
  background: #f3f4f9;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  display: grid;
  align-items: center;
  justify-content: center;
}

.card-content {
  display: grid;
  grid-template-rows: repeat(3, auto);
  grid-template-columns: repeat(2, 1fr);
  grid-row-gap: 5px;
  align-items: center;
}

.card-right {
  justify-self: right;
}

.subtext {
  color: #babecb;
}

.budget-dolar-text {
  height: fit-content;
}

.budget-bar {
  display: grid;
  grid-template-rows: 5px;
  grid-template-columns: auto auto;
  grid-column: 1 / -1;
}

.budget-bar > * {
  grid-row: 1 / -1;
}

.total-bar {
  background-color: #f8f9fb;
  grid-column: 1 / -1;
}

.used-bar {
  background-color: #4a00e0;
  grid-column: 1 / -1;
}

.transaction-card {
  grid-column: 2 / -1;
  display: grid;
  grid-row-gap: 15px;
}

.transaction {
  display: grid;
  grid-template-rows: repeat(2, fit-content);
  grid-row-gap: 3px;
  grid-template-columns: auto 3fr 1fr;
  grid-column-gap: 7px;
  align-items: center;
}

.trans-icon {
  color: #48c154;
  font-size: 0.6rem;
}

.trans-date {
  grid-column: 2 / 3;
}

.hidden {
  display: none;
}

/* END CARD STYLES */

.footer {
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  grid-template-columns: 1fr;
  justify-items: center;
  grid-row-gap: 15px;
  padding-top: 20px;
  grid-row-end: 4;
}

.footer > .logo-box {
  justify-self: center;
}
</style>
