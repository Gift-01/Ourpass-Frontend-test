<template>
  <div class="total-inflow">
    <p class="total regular-italic text-warning">{{ title }}</p>
    <p class="amount medium">{{ amount }}</p>
    <p class="flow text-warning regular-italic">{{ description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Total InFlow",
    },
    amount: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      default: "This is the total amount received during this period",
    },
  },
};
</script>

<style scoped>
.flow {
  font-size: 12px;
  font-weight: 400;
}

@media (max-width: 767px) {
  .total {
    font-size: 18px;
    font-weight: 500;
    margin-bottom: -8px;
  }

  .amount {
    margin-bottom: -4px;
    font-size: 22px;
    font-weight: 500;
  }

  .flow {
    font-size: 14px;
    font-weight: 500;
  }
}

@media (min-width: 768px) and (max-width: 1199px) {
  .total {
    font-size: 18px;
    font-weight: 500;
    /* margin-bottom: -8px; */
  }

  .amount {
    /* margin-bottom: -4px; */
    font-size: 29px;
  }
  .flow {
    font-size: 9px;
    font-weight: 800;
  }
}
</style>
