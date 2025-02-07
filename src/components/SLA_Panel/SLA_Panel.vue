<template>
  <div class="sla">
    <div class="sla__header">
      <span class="sla__title">SLA панель</span>
      <ButtonGroup class="sla__options" :buttons="selectOptions" />
    </div>
    <StatList :stats="stats" />

    <div class="sla__content">
      <StatTime class="sla__content-item" title="Среднее время ответа" time="1ч 20м" theme="medium" :percent="70" tooltipText="-53%" infoTooltipText="Content" />
      <StatTime class="sla__content-item" title="Время реакции" time="0ч 15м" theme="fast" :percent="15" tooltipText="-77%" infoTooltipText="Content" />
    </div>
  </div>
</template>

<script setup>
import ButtonGroup from './components/ButtonGroup.vue';
import StatList from './components/StatList.vue';
import StatTime from './components/StatTime.vue';

// Опции выбора
const selectOptions = [
  {
    name: 'День',
    id: 1,
  },
  {
    name: 'Неделя',
    id: 2,
  },
  {
    name: 'Месяц',
    id: 3,
  },
  {
    name: 'Все время',
    id: 4,
  },
];

// Статистика
const stats = [
  {
    id: 1,
    name: 'Обращений',
    number: 120,
  },
  {
    id: 2,
    name: 'В работе',
    number: 4,
  },
  {
    id: 3,
    name: 'Отложено',
    number: 32,
  },
  {
    id: 3,
    name: 'Завершено',
    number: 82,
  },
]
</script>

<style lang="scss" scoped>
.sla {
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 32px;
  border-radius: 30px;
  background-color: $background-base;

  &__header {
    display: flex;
    gap: 21px;
    justify-content: space-between;
  }

  &__title {
    font-size: 24px;
    line-height: 32px;
    font-weight: 500;
  }

  &__content {
    width: 100%;
    display: flex;
    gap: 14px;

    &-item {
      width: 100%;
    }
  }
}

@media screen and (max-width: 650px) {
  .sla{
    &__header {
      flex-direction: column;
      justify-content: center;
      gap: 5px;
    }

    &__options {
    width: 100%;
    justify-content: center;
    }

    &__content {
      flex-wrap: wrap;
      font-size: 16px;
    }
  }
}
</style>