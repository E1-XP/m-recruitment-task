<script setup lang="ts">
export interface HeaderData {
  heading: string;
  subtitle: string;
  subtitle2: string;
}

defineProps<{ data: HeaderData }>();
</script>

<template>
  <header class="header">
    <h2 class="heading h-text-center">{{ data.heading }}</h2>
    <p class="subtitle h-text-center header__subtitle">
      {{ data.subtitle }}
    </p>
    <p class="subtitle-2">
      {{ data.subtitle2 }}
    </p>
  </header>
</template>

<style scoped lang="scss">
.header {
  width: 22.23rem;

  &__subtitle {
    width: 85%;
    margin: 0 auto;
    margin-top: 1.1rem;
    margin-bottom: 0.91rem;
  }
}
</style>
