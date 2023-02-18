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
      :class="{ 'feature-cards__item--active': idx === 1 }"
      v-for="(card, idx) in cardData"
      v-bind:key="card.title"
    >
      <a href="#" class="card">
        <span
          class="card__icon"
          :class="{
            'card__icon--danger': idx === 1,
            'card__icon--success': idx === 2,
          }"
        >
          <fingerprintIcon v-if="idx === 0" />
          <lockIcon v-if="idx === 1" />
          <profileSettingsIcon v-if="idx === 2" />
        </span>
        <h3
          class="subtitle card__title"
          :class="{
            'card__title--danger': idx === 1,
            'card__title--success': idx === 2,
          }"
        >
          {{ card.title }}
        </h3>
        <p class="subtitle-2 card__subtitle">
          {{ card.text }}
        </p>
      </a>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.feature-cards {
  width: 23rem;
  justify-self: end;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-top: 1.792rem;
  margin-bottom: 3.583rem;

  &__item {
    border-radius: 4px;

    &--active {
      box-shadow: $box-shadow;
    }
  }
}

.card {
  display: grid;
  grid-template-columns: 2.708rem auto;
  grid-template-rows: auto auto;
  padding: 1rem;
  padding-right: 1.1rem;

  &__icon {
    width: 2.708rem;
    height: 2.708rem;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid $color-primary;
    border-radius: 4px;

    &--danger {
      border-color: $color-danger;
    }

    &--success {
      border-color: $color-success;
    }
  }

  &__title {
    font-size: 1rem;
    align-self: center;
    margin-left: 1.175rem;
    font-weight: 500;
    color: $color-primary;

    &--danger {
      color: $color-danger;
    }

    &--success {
      color: $color-success;
    }
  }

  &__subtitle {
    font-size: 0.667rem;
    font-family: "Inter", sans-serif;
    grid-column: 1/3;
    margin-top: 1.242rem;
  }
}
</style>
