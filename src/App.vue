<template>
  <div class="container">
    <SLA_Panel class="sla-panel" />
  </div>
</template>

<script setup>
import SLA_Panel from './components/SLA_Panel/SLA_Panel.vue';
import './styles/reset.scss';
</script>

<style lang="scss">
#app {
  font-family: 'Geologica', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $body-text;
  background-color: $gray-overlay-100;
  min-height: 100vh;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.sla-panel {
  width: 100%;
  max-width: 672px;
  margin: 15px;
}
</style>
