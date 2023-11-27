<script>
import MainCard from './MainCard.vue';
import { store } from '../store.js';

export default {
    components: {
        MainCard,
    },
    data () {
        return {
            store
        }
    },
}
</script>

<template>
    <main class="container-lg">
        <div class="row">
            <div class="col">
                <MainCard v-for="card in cards" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;
</style>
