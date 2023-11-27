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
        <div class="row justify-content-start align-items-center g-5">
            <div class="col-3 p-2" v-for="card in store.cards">
                <MainCard  :name="card.name" :imagePath="card.card_images[0].image_url" :type="card.type" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;

</style>
