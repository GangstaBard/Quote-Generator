<template>
  <section class="quote">
    <button @click="getQuote" class="quote__btn">Get new quote</button>
    <p class="quote__text">
      <i>{{ currentQuote }}</i>
    </p>
  </section>
</template>

<style lang="scss">
.quote {
  &__text {
    font-size: larger;
  }
  &__btn {
    padding: 10px;
    border-radius: 2em;
    background-image: linear-gradient(to right, #6ec0ac, #bd6a6a);

    color: #f0ebeb;
    font-weight: 600;
    transition: all 0.4s;

    &:hover {
      transform: scale(1.2);
    }
  }
}
</style>

<script>
export default {
  data() {
    return {
      currentQuote: '',
      currentCategory: '',
    }
  },
  methods: {
    async getQuote() {
      const response = await fetch('https://api.quotable.io/random')
      const quote = await response.json()
      this.currentQuote = quote.content
    },
  },
  mounted() {
    this.getQuote()
  },
}
</script>
