<template>
  <section class="quote">
    <form>
      <h3>You can choose a category for quotes!</h3>
      <input
        v-model="currentCategory"
        id="category"
        type="text"
        placeholder="category"
      />
      <p>Current category: {{ currentCategory }}</p>
    </form>

    <button @click="getQuote" class="quote__btn">Get new quote</button>
    <p class="quote__text">
      <i>{{ currentQuote }}</i>
    </p>
  </section>
</template>

<style lang="scss">
form {
  margin-bottom: 8vh;
}

input {
  padding: 0.5vw;
  border-radius: 1em;
}

.quote {
  &__text {
    margin: 1em;
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
      if (this.currentCategory != undefined) {
        const response = await fetch(
          'https://api.quotable.io/random?tags=' + this.currentCategory
        )
        const quote = await response.json()
        this.currentQuote = quote.content
      } else {
        const response = await fetch('https://api.quotable.io/random')
        const quote = await response.json()
        this.currentQuote = quote.content
      }
    },
  },

  mounted() {
    this.getQuote()
  },
}
</script>
