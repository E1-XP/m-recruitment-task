<script setup lang="ts">
import FingerprintIcon from "./icons/fingerprintIcon.vue";
import LockIcon from "./icons/lockIcon.vue";
import ProfileSettingsIcon from "./icons/profileSettingsIcon.vue";

export interface ActionData {
  title: string;
  text: string;
}

defineProps<{ data: ActionData; idx: number }>();
</script>

<template>
  <a href="#" class="card">
    <span
      class="card__icon"
      :class="{
        'card__icon--danger': idx === 1,
        'card__icon--success': idx === 2,
      }"
    >
      <FingerprintIcon v-if="idx === 0" />
      <LockIcon v-if="idx === 1" />
      <ProfileSettingsIcon v-if="idx === 2" />
    </span>
    <h3
      class="subtitle card__title"
      :class="{
        'card__title--danger': idx === 1,
        'card__title--success': idx === 2,
      }"
    >
      {{ data.title }}
    </h3>
    <p class="subtitle-2 card__subtitle">
      {{ data.text }}
    </p>
  </a>
</template>

<style lang="scss" scoped>
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
