<template>
  <header>
    <h1>Best quotes of all times!</h1>
  </header>
  <main><QuoteGenerator /></main>
</template>

<script>
import QuoteGenerator from "@/components/QuoteGenerator.vue";

export default {
  name: "App",
  components: {
    QuoteGenerator,
  },
};
</script>

<style lang="scss">
body {
  background-image: linear-gradient(to right, #a9f1df, #ffbbbb);
}

main {
  height: 80vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>
