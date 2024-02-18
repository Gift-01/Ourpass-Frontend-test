<template>
  <div>
    <q-item clickable class="q-md-mx-1 q-md-my-10" style="min-height: 40px">
      <q-item-section v-if="img || icon" avatar style="min-width: 0px">
        <q-img
          v-if="img"
          class=""
          :src="img"
          style="width: 18px; height: 18px; opacity: 80%"
        />
        <q-icon v-if="icon" :name="icon" />
      </q-item-section>

      <q-item-section>
        <q-item-label class="regular text-warning">{{ title }}</q-item-label>
      </q-item-section>
    </q-item>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "EssentialLink",
  props: {
    title: {
      type: String,
      required: true,
    },

    caption: {
      type: String,
      default: "",
    },

    link: {
      type: String,
      default: "#",
    },

    icon: {
      type: String,
      default: "",
    },

    img: {
      type: String,
      default: "",
    },
  },
});
</script>
