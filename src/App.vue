<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store.js';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store
    }
  },
  created() {
    this.store.loading = true;
    axios
      .get(this.store.apiLink)
      .then((resp) => {
        // console.log(resp.data.data);
        this.store.cards = resp.data.data;
        // console.log(this.store, this.store.cards);
        this.store.loading = false;
      });
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use './style/partials/variables' as *;
@use './style/general.scss';
</style>
