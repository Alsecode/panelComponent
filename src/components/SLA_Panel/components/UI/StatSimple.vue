<template>
  <div class="stat">
    <span class="stat__name">{{ name }}</span>
    <span class="stat__number">{{ number }}</span>
  </div>
</template>

<script setup>
// Название статистики, количество
const props = defineProps({
  name: {
    type: String,
    required: true,
  },
  number: {
    type: Number,
    required: true,
  },
})
</script>

<style lang="scss" scoped>
.stat {
  display: flex;
  flex-direction: column;
  gap: 4px;
  
  &__name {
    font-size: 20px;
    line-height: 28px;
    color: $tertiary-text;
    text-align: left;
  }

  &__number {
    font-size: 24px;
    line-height: 32px;
    font-weight: 500;
    max-width: fit-content;
  }
}
</style>