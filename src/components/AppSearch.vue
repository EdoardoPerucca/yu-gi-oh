<script>
import { store } from '../store';


export default {

    name: "AppSearch",

    data() {
        return {
            store,
        }
    },


    emits: ['userSearch'],

}
</script>

<template>
    <div id="search-nav">
        <input v-model="store.cardSearch" type="text" placeholder="Cerca la tua carta" @keyup.enter="$emit('userSearch')">
        <button @click="$emit('userSearch')">Cerca</button>
    </div>
</template>

<style lang="scss" scoped>
#search-nav {
    padding: 3em;

    input {
        padding: .5em 1em;
        border-radius: 25px;
        margin-right: 2em;
    }

    button {
        padding: .5em 1em;

        border-radius: 25px;
    }
}
</style>