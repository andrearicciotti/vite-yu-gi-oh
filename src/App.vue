<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppSearch from './components/AppSearch.vue';
import AppCounter from './components/AppCounter.vue';
import { store } from './store.js';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
    AppSearch,
    AppCounter,
  },
  data() {
    return {
      store
    }
  },
  created() {
    this.handleCreated()
  },
  methods: {
    handleSearch() {
      console.log('ok');
      this.store.loading = true;
      this.store.searchInput === '' ? this.handleCreated() :
        axios
          .get(this.store.apiLink, {
            params: {
              archetype: this.store.searchInput,
            },
          })
          .then((resp) => {
            this.store.cards = resp.data.data;
            this.store.loading = false;
          });
    },
    handleCreated() {
      this.store.loading = true;
      axios
        .get(this.store.apiLink)
        .then((resp) => {
          // console.log(resp.data.data);
          this.store.cards = resp.data.data;
          console.log(this.store, this.store.cards);
          this.store.loading = false;
        });
    }
  }
}
</script>

<template>
  <AppHeader />
  <AppSearch @search="handleSearch" />
  <AppMain />
  <AppCounter />
</template>

<style lang="scss">
@use './style/partials/variables' as *;
@use './style/general.scss';
</style>
