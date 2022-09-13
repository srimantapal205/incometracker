<template>
  <HeaderComounent />

  <router-view />
</template>
<script>
import HeaderComounent from "@/components/HeaderComounent.vue";
export default {
  name: "app-root",
  setup() {
    return {
      HeaderComounent,
    };
  },
};
</script>

