<template>
  <q-layout view="lHh Lpr lFf">
    <q-header bordered style="border: #f4f4f4 solid">
      <q-toolbar
        class="text-black bg-white justify-between q-py-md-16 q-px-md-40"
        style="height: 100px; border-bottom: 1px #f4f4f4"
      >
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          class="toggle-icon"
        />
        <q-toolbar-title class="regular-24 nav-title">
          Transactions
        </q-toolbar-title>
        <q-space />

        <div>
          <q-btn-dropdown
            flat
            label="last 30 days"
            class="bg-white text-black text-capitalize text-center justify-center q-py-md-8 q-px-md-12 regular w-119"
            style="width: 119px; border: 1px solid #e5e8eb"
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
        </div>

        <q-btn flat class="notification">
          <img src="../assets/Notification.svg" alt="bell" />
          <q-badge floating color="red" rounded />
        </q-btn>
        <q-btn flat class="notification">
          <img src="../assets/Vector.svg" alt="icon" />
        </q-btn>
        <div
          class="q-py-4 q-px-5"
          style="
            border: 1px solid #e5e8eb;
            width: 86px;
            display: flex;
            border-radius: 8px;
          "
        >
          <q-avatar>
            <img src="../assets/Passport.svg" alt="fff" />
          </q-avatar>
          <q-btn-dropdown flat style="">
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
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      :width="250"
      :class="$q.dark.isActive ? 'bg-grey-1' : 'bg-grey-1'"
    >
      <q-scroll-area class="fit regular">
        <q-list>
          <img
            alt="logo"
            src="~assets/Logo.svg"
            style="width: 138.48px; padding: 9.3px 5px; margin: 20px 7px"
          />

          <template v-for="(link, index) in essentialLinks" :key="index">
            <template v-if="!link.separator">
              <EssentialLink :key="link.title" v-bind="link" />
            </template>
            <template v-else>
              <q-separator :key="'separator' + index" />
            </template>
          </template>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";
import AdminSvg from "../assets/Admin.svg";
import AuditSvg from "../assets/Audit.svg";
import CrmSvg from "../assets/Crm.svg";
import LoansSvg from "../assets/Loans.svg";
import LogoutSvg from "../assets/Logout.svg";
import OverviewSvg from "../assets/Overview.svg";
import paymentSvg from "../assets/Payment.svg";
import RiskSvg from "../assets/Risk.svg";
import SupportSvg from "../assets/Support.svg";
import TransactionSvg from "../assets/Transaction.svg";

const linksList = [
  {
    title: "Overview",
    img: OverviewSvg,
  },
  {
    title: "Transactions",
    img: TransactionSvg,
  },
  {
    title: "Payments",
    img: paymentSvg,
  },
  {
    title: "Loans",
    img: LoansSvg,
  },
  {
    title: "Support",
    img: SupportSvg,
  },
  {
    title: "Risk Management",
    img: RiskSvg,
  },
  {
    title: "CRM",
    img: CrmSvg,
  },
  {
    title: "Admin",
    img: AdminSvg,
  },
  {
    separator: true,
  },

  {
    title: "Audit Log",
    img: AuditSvg,
  },
  {
    title: "Logout",
    img: LogoutSvg,
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value;
    };

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer,
      model: ref(null),
    };
  },
});
</script>

<style scoped>
.notification {
  width: 34px;
  height: 34px;
  border: 1px #e5e8eb;
  padding: 5px;
  border-radius: 12px;
  background-color: #fbfbfb;
  margin: 8px 12px 8px 12px;
}

@media (max-width: 767px) {
  /* .toggle-icon {
    display: none;
  } */

  .nav-title {
    display: none;
  }
}

@media (min-width: 768px) and (max-width: 1199px) {
  /* .toggle-icon {
    display: none;
  } */
}
</style>
