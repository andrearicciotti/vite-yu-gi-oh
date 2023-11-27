<script>
export default {

}
</script>

<template>
    <header>
        <div class="container-lg">
            <div class="logo">
                <img src="../assets/img/yu-gi-oh-logo.png" alt="">
            </div>
            <div class="title">
                <h1>Yu-Gi-Oh API</h1>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;

header {
    height: $header-heigth;
    background-color: $primary-color;
    color: $text-secondary;
    border-bottom: 2px solid $text-secondary;

    .container-lg {
        height: 100%;
        @include flex (row, space-around, center);

        .logo {
            height: 100%;

            img {
                display: block;
                height: 100%;
            }
        }

        .title {
            font-weight: 600;
        }
    }
}
</style>
