<template>
  <Header />
</template>

<script>
import Header from "./components/Header";

export default {
  components: {
    Header,
  },
  setup() {
    return {
      Header,
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
