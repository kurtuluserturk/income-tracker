<template>
  <div class="income-item">
    <div class="remove-item">X</div>
    <div class="desc">{{ income.desc }}</div>
    <div class="amount">€{{ income.amount }}</div>
    <div class="date">{{ income.date }}</div>
  </div>
</template>

<script>
export default {
  name: "IncomeItem",
  props: {
    income: Object,
  },
};
</script>

<style scoped>
.income-item {
  position: relative;
  display: flex;
  padding: 15px 15px 15px 0px;
  background-color: #fff;
  border-radius: 8px;
  max-width: 600px;
  margin: 0 auto 30px;
}
.remove-item {
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
.amount {
  color: #666;
  min-width: 100px;
  font-size: 20px;
}
.date {
  color: #666;
  text-align: right;
  font-size: 20px;
}
</style>
