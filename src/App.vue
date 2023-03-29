<script>
import { store } from "./store.js";
import axios from "axios";

import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';

export default {

  data() {
    return {
      store,
    }
  },
  components:
  {
    AppMain,
    AppLoader
  },

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
      console.log(res.data.data);
      this.store.cards = res.data.data;

      this.store.loading = false;
    });
  },
}
</script>

<template>
  <AppLoader v-if="store.loading"></AppLoader>

  <div>
    <AppMain></AppMain>
  </div>
</template>

<style lang="scss" scoped></style>