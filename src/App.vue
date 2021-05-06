<template>
  <div id="app">
    <Header/>
  </div>
</template>

<script>
import Header from'@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style lang="scss">
@import '~@fontsource/roboto/index.css';
@import '~@fontsource/roboto/700.css';
@import '@/styles/general.scss';
</style>
