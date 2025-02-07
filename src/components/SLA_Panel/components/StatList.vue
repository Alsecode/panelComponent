<template>
  <div class="stat-list">
    <Stat
      v-for="stat in stats"
      :name="stat.name"
      :number="stat.number"
      :key="stat.id"
    />
  </div>
</template>

<script setup>
import Stat from './UI/StatSimple.vue';

// Массив статистик (id, name, number)
const props = defineProps({
  stats: {
    type: Array,
    required: true,
  },
})
</script>

<style lang="scss" scoped>
.stat-list {
  display: flex;
  gap: 24px;
  justify-content: space-between;
  flex-wrap: wrap;
}
</style>