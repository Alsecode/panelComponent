<template>
  <TooltipSimple :theme="theme">
    <template #trigger>
      <div class="progress-bar">
        <div class="progress-bar__main"></div>
        <div class="progress-bar__filled" :class="`progress-bar__filled--${theme}`" :style="{ width: `${percent}%`}"></div>
      </div>
    </template>
    {{ text }}
  </TooltipSimple>
</template>

<script setup>
import TooltipSimple from './TooltipSimple.vue';

// Тема, процент заполненности, текст подсказки
const props = defineProps({
  theme: {
    type: String,
    required: true,
  },
  percent: {
    type: Number,
    required: true,
  },
  text: {
    type: String,
    required: true,
  },
})
</script>

<style lang="scss" scoped>
.progress-bar {
  position: relative;
  height: 10px;
  width: 100%;
  border-radius: 14px;

  &__main {
    background: $gray-line-20;
    width: 100%;
    height: 100%;
    border-radius: 14px;
  }

  &__filled {
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    border-radius: 14px;

    &--slow {
      background: $error;
    }

    &--medium {
      background: $primary;
    }

    &--fast {
      background: $success;
    }
  }
}
</style>