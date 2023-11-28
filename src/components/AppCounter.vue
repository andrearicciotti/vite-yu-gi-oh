<script>
import { store } from '../store.js';
export default {
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
<div class="row">
    <div class="col-12 my-3 text-center">
        <h2>In this page there are {{ store.cards.length }} cards.</h2>
        <p v-if="store.searchInput !== ''">Their archetype is '{{ store.searchInput }}'</p>
    </div>
</div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;

h2 {
    color: $text-secondary;
}

p {
    color: $text-primary;
}
</style>