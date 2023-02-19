<script setup lang="ts">
import Vue3Autocounter from "vue3-autocounter";

import DownloadIcon from "./icons/downloadIcon.vue";
import HeartIcon from "./icons/heartIcon.vue";
import UserIcon from "./icons/userIcon.vue";
import ReviewsIcon from "./icons/reviewsIcon.vue";

export interface StatisticsData {
  title: string;
  subtitle: string;
}

defineProps<{ data: StatisticsData; idx: number }>();
</script>

<template>
  <article class="feature-card">
    <span class="feature-card__icon">
      <DownloadIcon v-if="idx === 0" />
      <HeartIcon v-if="idx === 1" />
      <UserIcon v-if="idx === 2" />
      <ReviewsIcon v-if="idx === 3" />
    </span>
    <h3 class="feature-card__title">
      <Vue3Autocounter
        ref="counter"
        :startAmount="0"
        :endAmount="Number(data.title)"
        :suffix="Number(data.title) < 100 ? `K+` : `+`"
        separator=""
        decimalSeparator="."
        :duration="3"
        :autoinit="true"
      />
    </h3>

    <p class="feature-card__subtitle">
      {{ data.subtitle }}
    </p>
  </article>
</template>

<style lang="scss" scoped>
.feature-card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  &__icon {
    width: 1.892rem;
    height: 1.892rem;
    margin-bottom: 2.058rem;
  }

  &__title {
    font-size: 1.833rem;
    font-family: "Inter", sans-serif;
    font-weight: 500;
    margin-bottom: 1.192rem;
  }

  &__subtitle {
    font-size: 0.833rem;
    font-family: "Inter", sans-serif;
    font-weight: 500;
  }
}
</style>
