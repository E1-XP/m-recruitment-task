<script setup lang="ts">
import Header from "./header.vue";
import Slider from "./slider.vue";

const headerData = {
  heading: "Screenshots",
  subtitle: "Awesome Apps ScreenShots",
  subtitle2:
    "Most popular type of partnership Malta. The limited liability is, in fact, the only type of company allowed by Companies.",
};
</script>

<template>
  <section class="screenshots">
    <Header class="screenshots__header" :data="headerData" />
    <Slider />
  </section>
</template>

<style scoped lang="scss">
.screenshots {
  &__header {
    margin: 0 auto;
    margin-top: 2.667rem;
    margin-bottom: 1.821rem;
  }
}
</style>
