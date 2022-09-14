<template>
  <HeaderSection :totalIncome="state.totalIncome" />
  <CreateForm/>
  <!-- <router-view /> -->
</template>
<script>
import { reactive, computed } from "vue";
import HeaderSection from "@/components/HeaderSection.vue";
import CreateForm from "@/components/Form.vue";
export default {
  components: { HeaderSection, CreateForm },
  setup() {
   const state = reactive({
    income:[],
    totalIncome: computed(() => {
      let temp = 0;
      if (state.income.length>0) {
        for (let i = 0; i < state.income.length; i++) {
          temp += state.income[i].value
        }
      }
      return temp

    })
   });
    return {state};
  },
};
</script>
