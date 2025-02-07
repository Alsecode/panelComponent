<template>
  <div class="stat-time">
    <div class="stat-time__header">
      <span class="stat-time__title">{{ title }}</span>
      <TooltipSimple class="stat-time__info">
        <template #trigger>

            <svg class="stat-time__info-icon" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M8.00036 1.45461C7.14076 1.45461 6.28958 1.62392 5.49541 1.95288C4.70125 2.28183 3.97965 2.76399 3.37182 3.37182C2.76399 3.97965 2.28183 4.70125 1.95288 5.49541C1.62392 6.28958 1.45461 7.14076 1.45461 8.00036C1.45461 8.85996 1.62392 9.71115 1.95288 10.5053C2.28183 11.2995 2.76399 12.0211 3.37182 12.6289C3.97965 13.2367 4.70125 13.7189 5.49541 14.0479C6.28958 14.3768 7.14076 14.5461 8.00036 14.5461C9.7364 14.5461 11.4013 13.8565 12.6289 12.6289C13.8565 11.4013 14.5461 9.7364 14.5461 8.00036C14.5461 6.26432 13.8565 4.59938 12.6289 3.37182C11.4013 2.14425 9.7364 1.45461 8.00036 1.45461ZM0 8.00036C0 3.58125 3.58198 0 8.00036 0C12.4187 0 16.0007 3.58198 16.0007 8.00036C16.0007 12.418 12.4187 16 8.00036 16C3.58198 16 0 12.418 0 7.99964V8.00036ZM8.9095 4.54566C8.9095 4.78678 8.81371 5.01802 8.64322 5.18851C8.47272 5.35901 8.24148 5.45479 8.00036 5.45479C7.75925 5.45479 7.52801 5.35901 7.35751 5.18851C7.18701 5.01802 7.09123 4.78678 7.09123 4.54566C7.09123 4.30454 7.18701 4.0733 7.35751 3.90281C7.52801 3.73231 7.75925 3.63653 8.00036 3.63653C8.24148 3.63653 8.47272 3.73231 8.64322 3.90281C8.81371 4.0733 8.9095 4.30454 8.9095 4.54566ZM7.27306 6.54575C7.08016 6.54575 6.89517 6.62238 6.75878 6.75878C6.62238 6.89517 6.54575 7.08016 6.54575 7.27306C6.54575 7.46595 6.62238 7.65094 6.75878 7.78734C6.89517 7.92374 7.08016 8.00036 7.27306 8.00036V11.6369C7.27306 11.8298 7.34968 12.0148 7.48608 12.1512C7.62248 12.2876 7.80747 12.3642 8.00036 12.3642C8.19326 12.3642 8.37825 12.2876 8.51465 12.1512C8.65104 12.0148 8.72767 11.8298 8.72767 11.6369V7.27306C8.72767 7.08016 8.65104 6.89517 8.51465 6.75878C8.37825 6.62238 8.19326 6.54575 8.00036 6.54575H7.27306Z" color="currentColor"/>
            </svg>

        </template>
      {{ infoTooltipText }}
    </TooltipSimple>
    </div>

    <div class="stat-time__content">
      <span class="stat-time__time">{{ time }}</span>
      <ProgressBar class="stat-time__progress" :theme="theme" :percent="percent" :text="tooltipText" />
    </div>
  </div>
</template>

<script setup>
import ProgressBar from './UI/ProgressBar.vue';
import TooltipSimple from './UI/TooltipSimple.vue';

// Заголовок карточки, время, тема, процет заполненности, текст подсказки, текст инфо-подсказки 
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  time: {
    type: String,
    required: true,
  },
  theme: {
    type: String,
    required: true,
  },
  percent: {
    type: Number,
    required: true,
  },
  tooltipText: {
    type: String,
    required: true,
  },
  infoTooltipText: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.stat-time {
  display: flex;
  flex-direction: column;
  gap: 4px;
  
  padding: 16px;
  border-radius: 20px;
  background: $background-secondary;

  &__header {
    display: flex;
    gap: 12px;
    justify-content: space-between;
    align-items: center;
  }

  &__title {
    font-size: 20px;
    line-height: 28px;
    color: $tertiary-text;
    text-align: left;
  }

  &__info {
    width: 16px;
    height: 16px;
    flex-shrink: 0;

    &-icon {
      fill: $gray-icon-50;

      &:hover {
        fill: $gray-90;
      }
    }
  }

  &__content {
    display: flex;
    gap: 4px;
    justify-content: space-between;
    align-items: center;
  }

  &__time {
    font-size: 24px;
    line-height: 32px;
    font-weight: 500;
  }

  &__progress {
    width: 60%;
  }
}
</style>
