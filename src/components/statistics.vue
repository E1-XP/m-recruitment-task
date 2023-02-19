<script setup lang="ts">
import FeatureCard from "./featureCard.vue";

import Shape1 from "./backgrounds/shape1.vue";
import Shape2 from "./backgrounds/shape2.vue";

const data = [
  { title: "25", subtitle: "App Downloads" },
  {
    title: "1200",
    subtitle: "Happy Clients",
  },
  { title: "14", subtitle: "Active User" },
  { title: "3500", subtitle: "Total Reviews" },
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
    <Shape1 class="statistics__shape1" />
    <Shape2 class="statistics__shape2" />
  </section>
</template>

<style scoped lang="scss">
.statistics {
  background-color: $color-primary;
  color: $color-white;
  padding: 8.76rem 0;
  clip-path: polygon(0 0, 100% 10%, 100% 100%, 0 90%);
  position: relative;

  &__container {
    display: flex;
  }

  &__list {
    display: flex;
    justify-content: space-evenly;
    width: 68%;
    margin: 0 auto;

    @include bp($bp-small) {
      flex-direction: column;
      height: 48rem;
    }
  }

  &__shape1 {
    position: absolute;
    bottom: 26%;
    transform: scale(221%) translateX(28%) translateY(-16%);
    z-index: -1;

    @include bp($bp-very-large) {
      transform: scale(169%) translateX(22%);
    }

    @include bp($bp-medium) {
      transform: initial;
    }

    @include bp($bp-small) {
      display: none;
    }
  }

  &__shape2 {
    position: absolute;
    bottom: 6%;
    right: 0;
    transform: scale(140%) translateX(-15%) translateY(-13%);
    z-index: -1;

    @include bp($bp-large) {
      transform: initial;
    }

    @include bp($bp-small) {
      display: none;
    }
  }
}
</style>
