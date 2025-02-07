<template>
  <div class="tooltip-wrapper" @mouseenter="showTooltip" @mouseleave="hideTooltip"   >
    <slot name="trigger" class="trigger"></slot>
      <div
        v-if="visible"
        class="tooltip-content"
        :class="`tooltip-content--${theme}`"
      >
        <slot></slot>
      </div>
  </div>
</template>

<script setup>
import { ref, defineProps } from 'vue'

// Тема для подсказки
const props = defineProps({
  theme: {
    type: String,
    required: false,
  },
});

// Управление показом тултипа
const visible = ref(false);
const showTooltip = () => visible.value = true;
const  hideTooltip = () => visible.value = false;
</script>

<style lang="scss" scoped>
.tooltip-wrapper {
  position: relative;
}

.tooltip-content {
  position: absolute;
  bottom: calc(100% + 8px);
  right: 50%;
  transform: translateX(50%);

  font-size: 16px;
  line-height: 24px;
  font-weight: 300;

  padding: 4px 8px;
  background: $gray-90;
  color: $gray-5;
  border-radius: 6px;
  box-shadow: 0px 1px 4px -1px $gray-90_30;

  &--slow {
    border: 1px solid $error-50;
    background: $error-10;
  }

  &--medium {
    border: 1px solid $primary-50;
    background: $primary-10;
  }

  &--fast {
    border: 1px solid $success-50;
    background: $success-10;
  }

  &--slow, &--medium, &--fast {
    color: $body-text;
    padding: 6px 10px;
    font-size: 24px;
    line-height: 32px;
    font-weight: 500;
    box-shadow: none;
  }

  &::before {
    position: absolute;
    content: "";
    width: 0;
    height: 0;
    border-left: 6px solid transparent;
    border-right: 6px solid transparent;
    border-top: 6px solid $gray-90;
    left: 50%;
    bottom: -11px;
    transform: translateY(-100%) translateX(-50%);
  }

  &--slow::before {
    border-top: 6px solid $error;
  }

  &--medium::before {
    border-top: 6px solid $primary;
  }

  &--fast::before {
    border-top: 6px solid $success;
  }
}
</style>