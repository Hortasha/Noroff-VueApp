<template>
  <div id="app" class="container">
    <MainPage />
  </div>
</template>

<script>
import MainPage from './components/container/MainPage';

export default {
  name: 'app',
  components: {
    MainPage
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
