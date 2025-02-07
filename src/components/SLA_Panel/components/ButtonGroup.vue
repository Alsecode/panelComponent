<template>
  <div class="btn-group">
    <ButtonSimple
      v-for="button in buttons"
      :key="button.id"
      :text="button.name"
      :id="button.id"
      :isActive="button.id === activeBtnId ? true : false"
      @setActive="setActive"      
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ButtonSimple from './UI/ButtonSimple.vue';

// Массив кнопок
const props = defineProps({
  buttons: {
    type: Array,
    required: true,
  },
})

// Id активной кнопки
const activeBtnId = ref(1);

// Установка активной кнопки
const setActive = (id) => activeBtnId.value = id;
</script>

<style lang="scss" scoped>
.btn-group {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}
</style>