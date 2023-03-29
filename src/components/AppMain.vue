<script>

import { store } from "../store.js";

import CardItem from "./CardItem.vue";

import CardCounter from "./CardCounter.vue";

export default {

    name: "AppMain",
    data() {
        return {
            store,
        }
    },

    components: {
        CardItem,
        CardCounter,
    },

}
</script>
  
<template>
    <div id="main-container">

        <em>
            <h1>Card Yu Gi Oh</h1>
        </em>

        <div>
            <input type="text" placeholder="Inserisci un nome">
            <button>Cerca</button>
        </div>

        <div id="card-list">
            <CardItem v-for="card in store.cards" :card="card"></CardItem>
            <CardCounter></CardCounter>
        </div>

    </div>
</template>

<style lang="scss" scoped>
#main-container {
    display: flex;
    flex-direction: column;
    text-align: center;
    max-width: 1000px;
    margin: auto;
    padding-top: 50px;
    gap: 2em;

    h1 {
        text-transform: uppercase;
        color: blue;
        font-size: 2.5em;
    }


    #card-list {
        display: flex;
        flex-flow: row wrap;
        justify-content: center;
        gap: 20px;
    }
}
</style>
