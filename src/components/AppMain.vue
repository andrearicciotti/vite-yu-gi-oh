<script>
import MainCard from './MainCard.vue'
export default {
    components : {
        MainCard,
    },

}
</script>

<template>
<main class="container-lg">
    <div class="row">
        <div class="col">
            <MainCard />
        </div>
    </div>
</main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;


</style>
