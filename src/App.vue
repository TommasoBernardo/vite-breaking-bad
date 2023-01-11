<template>
  <AppHeader />
  <AppMain />
</template>
<script>
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store,
    }
  },
}
</script>
<style lang="scss">
@use './styles/partials/general.scss' as *;
@use 'bootstrap/scss/bootstrap.scss' as *;
</style>