<script setup lang="ts">
import fingerprintIcon from "./icons/fingerprintIcon.vue";
import lockIcon from "./icons/lockIcon.vue";
import profileSettingsIcon from "./icons/profileSettingsIcon.vue";

const cardData = [
  {
    title: "Install the App",
    text: "Big, small, online, offline, local or international. Size doesn’t matter. We work on diverse projects for top brands.",
    icon: "fingerprintIcon",
  },
  {
    title: "Login First",
    text: "Most popular type of partnership. limited liabilities, Size doesn’t work on diverse projects for top brands.",
    icon: "lockIcon",
  },
  {
    title: "Setup Your Profile",
    text: "Popular type of partnership. limited liabilities, in fact, the only Size doesn’t matter. diverse projects for top brands.",
    icon: "profileSettingsIcon",
  },
];
</script>

<template>
  <ul class="feature-cards">
    <li
      class="feature-cards__item"
      v-for="(card, idx) in cardData"
      v-bind:key="card.title"
    >
      <a href="#" class="card">
        <span class="card__icon">
          <fingerprintIcon v-if="idx == 0" />
          <lockIcon v-if="idx == 1" />
          <profileSettingsIcon v-if="idx == 2" />
        </span>
        {{ card.title }}
      </a>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.feature-cards {
}

.card {
  &__icon {
    border: 1px solid $color-primary;
  }
}
</style>
