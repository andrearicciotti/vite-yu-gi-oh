<script>
import { store } from '../store.js';
import LoaderMain from './LoaderMain.vue';
import MainCard from './MainCard.vue';

export default {
    components: {
        LoaderMain,
        MainCard,
    },
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <main class="container-lg">
        <LoaderMain v-if="store.loading" />
        <div class="row justify-content-start align-items-center g-5" v-else>
            <div class="col-3 p-2" v-for="card in store.cards">
                <MainCard :name="card.name" :imagePath="card.card_images[0].image_url" :archetype="card.archetype" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;
</style>
