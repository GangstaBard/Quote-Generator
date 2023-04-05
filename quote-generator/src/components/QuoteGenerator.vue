<template>
  <section class="quote">
    <button class="quote__btn">Get new quote</button>
    <p class="quote__text">
      <i
        >"Success is not final; failure is not fatal: It is the courage to
        continue that counts."</i
      >
    </p>
  </section>
</template>

<style lang="scss">
.quote {
  &__text {
  }

  &__btn {
    padding: 1%;
    border-radius: 1em;
    background-color: red;
    color: #fff;
    font-weight: 600;
    transition: all 0.3s;

    &:hover {
      transform: scale(1.2);
    }
  }
}
</style>

<script>
export default { name: "QuoteGenerator" };
</script>
