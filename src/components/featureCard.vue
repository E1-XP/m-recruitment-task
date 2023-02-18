<script setup lang="ts">
import DownloadIcon from "./icons/downloadIcon.vue";
import HeartIcon from "./icons/heartIcon.vue";
import UserIcon from "./icons/userIcon.vue";
import ReviewsIcon from "./icons/reviewsIcon.vue";

import type { StatisticsData } from "./../interfaces";

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
      {{ data.title }}
    </h3>
    <p class="feature-card__subtitle">
      {{ data.subtitle }}
    </p>
  </article>
</template>

<style lang="scss" scoped>
.feature-card {
}
</style>
