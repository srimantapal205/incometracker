<template>
    <div class="incomeList">
        <IncomeItem v-for="item in state.income" :key="item.id" :income="item" @remove="removeItem"/>
    </div>
</template>

<script>
import IncomeItem from '@/components/IncomeItem.vue';

    
export default {
    components: {
        IncomeItem,
    },
    props: {
        state: Object
    },
    setup(props, {emit}){
        function removeItem(id) {
            emit ("remove", id)
        }


        return {
            removeItem
        }
    }
}
</script>

<style lang="scss" scoped>
    .incomeList {
        margin-top: 30px;
        padding: 15px;
    }

</style>