<template>
  <header class="header">
    <h1>Income Trccker</h1>
    <div class="totalIncome">&euro;{{totalIncome}}</div>
  </header>
</template>

<script>
export default {
  name: "HeaderSection",
  props: {
    totalIncome: Number,
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
  background-color: #313131;
  border-bottom: 5px solid #ffce00;
  h1 {
    color: #eee;
    font-size: 28px;
  }
  .totalIncome {
    font-family: "Fira Code", "Fira Sans", sans-serif;
    background-color: #ffce00;
    color: #fff;
    font-size: 20px;
    font-weight: 900;
    padding: 5px 10px;
    min-width: 100px;
    text-align: center;
    border-radius: 8px;
    box-shadow: inset 0px 0px 6px rgba(0, 0, 0, 0.25);
    text-shadow: 0px 3px 3px rgba(0, 0, 0, 0.25);
  }
}
</style>
