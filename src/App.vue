<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';

export default {
  components: {
    AppHeader,
  },

  created() {
    axios
    .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
    .then((resp) => {
      console.log(resp);
    });
  }
}
</script>

<template>
  <AppHeader />
</template>

<style lang="scss">
@use './style/partials/variables' as *;
@use './style/general.scss';
</style>
