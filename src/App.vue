<template>
  <div id="app" :class="[$style.wrapper]">
    <img alt="Vue logo" src="./assets/logo.png" />
    <header>
      <h1>My personal costs</h1>
    </header>
    <main>
      <AddPayment @addNewPayment="addData" />
      <br />
      <PaymentDisplay :list="paymentList" />
      <Pagination />
    </main>
  </div>
</template>

<script>
import PaymentDisplay from "./components/PaymentDisplay.vue";
import AddPayment from "./components/AddPayment.vue";
import Pagination from "./components/Pagination.vue";

export default {
  name: "App",
  components: {
    PaymentDisplay,
    AddPayment,
    Pagination
  },
  data: () => ({
    paymentList: [],
  }),
  methods: {
    addData(data) {
      this.paymentList.push(data);
    },
    fetchData() {
      return [
        {
          date: "28.03.2020",
          category: "Food",
          value: 169,
        },
        {
          date: "28.03.2020",
          category: "Sport",
          value: 150,
        },
      ];
    },
  },
  created() {
    this.paymentList = this.fetchData();
  },
};
</script>

<style lang="scss" module>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
div {
  margin-bottom: 20px;
}
.wrapper {
  margin: 0 auto;
}
</style>
