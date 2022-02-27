<template>
  <div class="income-list"></div>
  <IncomeItem
    v-for="data in state.sortedIncome"
    :key="data.id"
    :income="data"
  />
</template>

<script>
import IncomeItem from "./IncomeItem";

export default {
  name: "IncomeList",
  components: {
    IncomeItem,
  },
  props: {
    state: Object,
  },
  setup() {
    return {
      IncomeItem,
    };
  },
};
</script>

<style scoped>
.income-list {
  margin-top: 30px;
  padding: 15px;
}
</style>
