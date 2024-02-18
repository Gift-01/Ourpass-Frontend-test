<template>
  <div class="container">
    <main>
      <TotalFlow
        title="Total Inflow"
        amount="NGN 16,000.00"
        description="This is the total amount spent during this period"
      ></TotalFlow>

      <TotalFlow
        title="Total Outflow"
        amount="NGN 16,000.00"
        description="This is the total amount spent during this period"
      ></TotalFlow>
    </main>
    <TransactionSummary />
  </div>
</template>

<script>
import { ref } from "vue";
import TotalFlow from "./TotalFlow.vue";
import TransactionSummary from "./TransactionSummary.vue";

export default {
  components: { TotalFlow, TransactionSummary },
  setup() {
    return {
      text: ref(""),
      ph: ref(""),
      dense: ref(false),
    };
  },
};
</script>

<style scoped>
main {
  display: flex;
  margin: 25px 50px;
  gap: 350px;
}

.container {
  height: 256px;
}

@media (max-width: 767px) {
  main {
    display: block;
  }
}

@media (min-width: 768px) and (max-width: 1199px) {
  main {
    display: flex;
    margin: 26px 23px;
    gap: 350px;
  }

  .container {
    height: 256px;
  }
}
</style>
