<script setup lang="ts">
import FeatureCard from "./featureCard.vue";

const data = [
  { title: "25K+", subtitle: "App Downloads" },
  {
    title: "1200+",
    subtitle: "Happy Clients",
  },
  { title: "14K+", subtitle: "Active User" },
  { title: "3500+", subtitle: "Total Reviews" },
];
</script>

<template>
  <section class="statistics">
    <div class="l-container statistics__container">
      <ul class="statistics__list">
        <li
          class="statistics__item"
          v-for="(item, idx) in data"
          :key="item.title"
        >
          <FeatureCard :data="item" :idx="idx" />
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped lang="scss">
.statistics {
  background-color: $color-primary;
  color: $color-white;

  &__list {
    display: flex;
    justify-content: space-between;
  }
}
</style>
