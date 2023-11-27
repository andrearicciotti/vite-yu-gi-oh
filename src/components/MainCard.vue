<script>
export default {
props: {
    name: String,
    imagePath: String,
    type: String,
}

}
</script>

<template>
    <div class="card">

        <img :src="imagePath" :alt="name">
        <h5>{{  name  }}</h5>
        <p>{{  type  }}</p>

    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;

.card {
    background-color: $primary-color;
    color: $text-secondary;
    border: 2px solid $text-secondary;
    padding: 0 .2rem;

    img {
        display: block;
        height: 60%;
    }

    h5 {
        font-size: .9rem;
        padding: .5rem .2rem .2rem .2rem;
    }

    p {
        text-align: center;
        color: $text-primary;
        font-size: .7rem;
        border-top: 2px solid $secondary_color;
        margin-bottom: 0 !important;
    }
}


</style>