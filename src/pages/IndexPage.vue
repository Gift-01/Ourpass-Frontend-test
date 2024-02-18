<template>
  <q-page>
    <TransactionDashboard />
    <TheTable />
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import TheTable from "../components/TheTable.vue";
import TransactionDashboard from "src/components/TransactionDashboard.vue";

export default defineComponent({
  name: "IndexPage",
  components: {
    TheTable,
    TransactionDashboard,
  },
});
</script>
