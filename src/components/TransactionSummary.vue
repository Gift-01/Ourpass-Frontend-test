<template>
  <section class="row justify-around regular wrapper">
    <div class="transaction text-accent">Transactions: 634</div>

    <div>
      <q-input
        class="input justify-center items-center"
        standout
        bottom-slots
        v-model="text"
        label="Search using customer's email,phone Number, session ID or transaction ref"
        :dense="dense"
        label-color="#666"
      >
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
      </q-input>
    </div>
    <div
      style="display: flex; gap: 29px; padding: 8px 0; justify-content: center"
    >
      <div class="filter">
        <q-btn-dropdown
          flat
          icon="sort"
          label="Filter by "
          class="bg-white text-black drop-down"
          style="font-weight: 0; min-height: 0; text-transform: capitalize"
        >
          <q-list>
            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>Photos</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>Videos</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>Articles</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
        <div>
          <!-- <img
            src="../assets/filter.svg"
            alt="Filter-icon"
            width="20px"
            height="20px"
            style="color: red"
          /> -->
        </div>
      </div>
      <div>
        <!-- <img
          src="../assets/filter.svg"
          alt="filter-icon"
          width="20.24px"
          height="20px"
        /> -->
        <!-- <q-icon name="sort"/> -->
      </div>
      <section class="export justify-between row no-wrap bg-black">
        <img src="../assets/Export.svg" alt="Export-icon" width="18px" />
        <p class="text-white">Export</p>
      </section>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";

export default {
  components: {},
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
.wrapper {
  height: 58px;
}
.transaction {
  font-size: 15px;
  line-height: 24px;
  font-weight: 600;
  padding: 18px 0;
}

.export {
  width: 91px;
  height: 34px;
  border-radius: 5px;
  padding: 5px 10px;
  /* margin: 7px 0px; */
}

.export p {
  padding: 3px;
}

.input {
  width: 480px;
  height: 42px;
  gap: 10px;
}

.filter {
  border: 1px solid #fbfbfb;
  display: flex;
  border-radius: 5px;
  height: 36px;
  width: 125.94px;
}

.sort-filter-icon {
  display: none;
  color: red;
  background-color: blue;
}

@media (max-width: 767px) {
  .wrapper {
    height: 60px;
    flex-wrap: nowrap;
    justify-content: space-evenly;
    width: 100%;
  }

  .input {
    width: 115px;
  }

  .export {
    /* margin: 16px 0; */
    margin: 7px 0px;
    width: 32px;
  }

  .export p {
    display: none;
  }

  .filter {
    display: none;
  }
}

@media (min-width: 768px) and (max-width: 1199px) {
  .wrapper {
    height: 60px;
    /* flex-wrap: nowrap; */
    /* justify-content: space-evenly; */
    /* width: 100%; */
  }
  .input {
    width: 300px;
  }
}
</style>
