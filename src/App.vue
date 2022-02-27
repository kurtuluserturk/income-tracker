<template>
  <Header :totalIncome="state.totalIncome" />
  <Form @add-income="addIncome" />
  <IncomeList :state="state" />
</template>

<script>
import Header from "./components/Header";
import Form from "./components/Form";
import IncomeList from "./components/IncomeList";
import { reactive, computed } from "vue";

export default {
  components: {
    Header,
    Form,
    IncomeList,
  },
  setup() {
    const state = reactive({
      income: [],
      totalIncome: computed(() => {
        let temp = 0;

        if (state.income.length > 0) {
          for (let i = 0; i < state.income.length; i++) {
            temp += state.income[i].amount;
          }
        }

        return temp;
      }),

      sortedIncome: computed(() => {
        let temp = [];

        /* slice(0) was used to preserve the original array.
       slice makes a copy of the array, instead of mutating the orginal */
        // sort((a, b) => a - b )  ascending sorting,  b - a descending sorting
        temp = state.income.slice(0).sort((a, b) => a.amount - b.amount);

        return temp;
      }),
    });

    function addIncome(data) {
      // format date
      let d = data.date ? data.date.split("-") : "";
      let newDate = [d[2], d[1], d[0]].join(".");

      state.income = [
        ...state.income,
        {
          id: Date.now(), // In real project, this id comes from Database
          desc: data.desc,
          amount: data.amount,
          date: newDate,
        },
      ];
    }

    return {
      Header,
      Form,
      IncomeList,
      state,
      addIncome,
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Fira Sans", sans-serif;
}
body {
  background: #eee;
}
</style>
