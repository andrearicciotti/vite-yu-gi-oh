<script>
import { store } from '../store.js';
export default {
    data() {
        return {
            store,
        }
    },
    methods: {
        getSelected(event) {
            this.store.searchInput = event.target.value
            console.log(event.target.value, this.store.searchInput);
        }
    }
}
</script>

<template>
    <div class="row">
        <div class="col-12 my-3">
            <label class="mx-2 fw-semibold" for="archetype">Card Filter:</label>
            <select @change="getSelected($event)" name="archetype" id="archetype">
                <option value="">Choose</option>
                <option value="alien">Alien</option>
                <option value="allyOfJustice">Ally Of Justice</option>
                <option value="ancientGear">Ancient Gear</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;
@use '../style/partials/mixins' as *;

.col-12 {
    text-align: center;

    label {
        color: $text-secondary;
    }

    select {
        border: 2px solid $text-secondary;
        background-color: $text-secondary;
    }
}
</style>