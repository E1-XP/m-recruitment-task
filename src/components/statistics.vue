<script setup lang="ts">
import DownloadIcon from "./icons/downloadIcon.vue";
import HeartIcon from "./icons/heartIcon.vue";
import UserIcon from "./icons/userIcon.vue";
import ReviewsIcon from "./icons/reviewsIcon.vue";

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
          <article class="statistics__fact fact">
            <span class="fact__icon">
              <DownloadIcon v-if="idx === 0" />
              <HeartIcon v-if="idx === 1" />
              <UserIcon v-if="idx === 2" />
              <ReviewsIcon v-if="idx === 3" />
            </span>
            <h3 class="fact__title">
              {{ item.title }}
            </h3>
            <p class="fact__subtitle">
              {{ item.subtitle }}
            </p>
          </article>
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
