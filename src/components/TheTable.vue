<template>
  <div class="q-pa-md">
    <q-table
      class="my-sticky-dynamic"
      flat
      :rows="rows"
      :columns="columns"
      row-key="name"
      style="width: 100%; height: 584px"
    >
    </q-table>
  </div>
</template>

<script>
import { ref, computed } from "vue";
const columns = [
  {
    name: "name",
    required: true,
    label: "Customer Name",
    align: "left",
    field: (row) => row.name,
    format: (val) => `${val}`,
  },
  {
    name: "calories",
    align: "center",
    label: "Transaction ID",
    field: "calories",
  },
  { name: "fat", label: "Session ID", field: "fat" },
  {
    name: "carbs",
    label: "Transaction Type",
    field: "carbs",
  },
  {
    name: "protein",
    label: "Amount (NGN)",
    field: "protein",
  },
  {
    name: "sodium",
    label: "Payment Type",
    field: "sodium",
  },
  {
    name: "calcium",
    label: "Date",
    field: "calcium",
  },
];

const rows = [
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: " Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
  {
    name: "Gbohunmi Ajibesin",
    calories: 4092829,
    fat: 4092829,
    carbs: "Airtime",
    protein: "4,500.00",
    sodium: "pos Inflow",
    calcium: "Aug 12, 2020",
  },
];

export default {
  setup() {
    const currentPage = ref(1);
    const rowsPerPage = 5;

    const displayedRows = computed(() => {
      const startIndex = (currentPage.value - 1) * rowsPerPage;
      const endIndex = startIndex + rowsPerPage;
      return rows.slice(startIndex, endIndex);
    });

    const maxPages = Math.ceil(rows.length / rowsPerPage);

    return {
      columns,
      rows,
      currentPage,
      displayedRows,
      maxPages,
    };
  },
};
</script>

<style lang="sass">
.my-sticky-dynamic
  /* height or max-height is important */
  height: 410px

  .q-table__top,
  thead tr:first-child th /* bg color is important for th; just specify one */
    background-color: #fbfbfb


  /* this will be the loading indicator */
  thead tr:last-child th
    /* height of all previous header rows */
    top: 48px
  thead tr:first-child th
    top: 0

  /* prevent scrolling behind sticky top row on focus */
  tbody
    /* height of all previous header rows */
    scroll-margin-top: 48px

  tbody td
    padding: 30px /* Adjust this value as needed for the desired space between rows */
</style>
