<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss">
$background-base: #FFFFFF;
$background-secondary: #F4F5F7;
$background-tertiary: #EAECEF;

// grayscale
$gray-overlay-100: #192434;
$gray-90: #263446;
$gray-80: #414D5E;
$gray-70: #626D7C;
$gray-60: #77828F;
$gray-icon-50: #8993A0;
$gray-40: #A9B1BC;
$gray-30: #C4CBD3;
$gray-line-20: #DADFE4;
$gray-10: #E9ECF0;
$gray-5: #F3F5F7;

// text
$heading-text: #192434;
$body-text: #263445;
$secondary-text: #616D7C;
$tertiary-text: #8993A0;
$disabled-text: #C4CBD3;
$white-contrast-text: #FFFFFF;

// primary
$primary: #8649D4;
$primary-120: #53258E;
$primary-110: #652DAC;
$primary-50: #C89DFF;
$primary-10: #EAD9FF;
$primary-5: #F9F5FD;

// error
$error: #CF3232;
$error-120: #A01515;
$error-110: #B01818;
$error-50: #FF7878;
$error-10: #FFDEDE;
$error-5: #FFF6F6;

// warning
$warning: #F59E4E;
$warning-120: #9A5413;
$warning-110: #B55D0B;
$warning-50: #FFC690;
$warning-10: #FFF0E2;
$warning-5: #FFF6EE;

// success
$success: #08AA5E;
$success-120: #115A38;
$success-110: #117043;
$success-50: #88CEAD;
$success-10: #E0F9ED;
$success-5: #EFFBF5;

// shadows
$gray-90_30: rgba(#263446, 0.3);
$gray-90_20: rgba(#263446, 0.2);
$gray-90_10: rgba(#263446, 0.1);

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
