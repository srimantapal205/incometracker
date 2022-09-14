<template>
  <HeaderSection :totalIncome="state.totalIncome" />
  <CreateForm @addIncome="AddIncome" />
  <IncomeList :state="state" @remove = "removeItem" />
  <!-- <router-view /> -->
</template>
<script>
import { reactive, computed } from "vue";
import HeaderSection from "@/components/HeaderSection.vue";
import CreateForm from "@/components/Form.vue";
import IncomeList from "@/components/IncomeList.vue";

export default {
  components: { HeaderSection, CreateForm, IncomeList },
  setup() {
    const state = reactive({
      income: [],
      totalIncome: computed(() => {
        let temp = 0;
        if (state.income.length > 0) {
          for (let i = 0; i < state.income.length; i++) {
            temp += state.income[i].value;
          }
        }
        return temp;
      }),

    });
    function AddIncome(data) {
      let dt = data.date.split("-");
      let newDate = new Date(dt[0], dt[1], dt[2]);
      state.income = [
        ...state.income,
        {
          id: Date.now(),
          desc: data.desc,
          value: parseInt(data.value),
          date: newDate.getTime(),
        },
      ];
      console.log(state.income);
    }
    function removeItem(id){
      state.income = state.income.filter(x => x.id != id)
    }
    return { state, AddIncome, removeItem };
  },
};
</script>
<style lang="scss">
body {
  background-color: antiquewhite;
}
</style>
