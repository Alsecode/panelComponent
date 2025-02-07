<template>
  <button type="button" class="btn" @click="emit('setActive', id)" :class="{ 'btn--active': isActive }">
    {{ text }}
  </button>
</template>

<script setup>
// Текст в кнопке, id, активна ли кнопка
const props = defineProps({
  text: {
    type: String,
    requiured: true,
  },
  id: {
    type: Number,
    requiured: true,
  },
  isActive: {
    type: Boolean,
    required: false,
    default: false,
  },
});

const emit = defineEmits(['setActive']);

</script>

<style lang="scss" scoped>
.btn {
  padding: 4px 12px;
  font-size: 16px;
  line-height: 24px;
  font-weight: 300;
  text-align: center;
  border: 1px solid $gray-line-20;
  border-radius: 10px;
  background-color: $background-base;
  transition: 0.2s ease all;

  &--active {
    border-color: $primary-10;
    background-color: $primary-10;
  }
}
</style>