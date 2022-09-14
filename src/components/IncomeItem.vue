<template>
  <div class="incomeItemSection">
          <div class="removeItem" ><button @click="removeItem" >X</button></div>

          <div class="desc">{{income.desc}}</div>

          <div class="price">&euro;{{income.value}}</div>

          <div class="date">{{fullDate}}</div>
        </div>

</template>

<script>
export default {
  name: "IncomeList",
  props:{income:Object},
  setup(props, {emit}){
    let  dt = new Date(props.income.date)
    let day =  dt.getDate();
    let month = dt.getMonth();
    let year = dt.getFullYear();

    let fullDate = `${day}/ ${month}/ ${year}`;

    
    function removeItem(){
        emit ("remove", props.income.id); 
    }
    return {fullDate, removeItem}
  }

};
</script>

<style lang="scss" scoped>
.incomeItemSection {
  position: relative;
  display: flex;
  padding: 15px 15px 15px 0px;
  background-color: #fff;
  border-radius: 8px;
  max-width: 600px;
  margin: 0 auto 30px;
  .removeItem {
    color: #ef2d2d;
    font-weight: 600;
    font-size: 20px;
    line-height: 1;
    text-align: center;
    margin: 0 15px;
  }
  .desc {
    color: #666;
    flex: 1 1 100%;
    font-size: 20px;
  }
  .price {
    color: #666;
    min-width: 100px;
    font-size: 20px;
  }
  .date {
    color: #666;
    text-align: right;
    font-size: 20px;
  }
}
</style>
