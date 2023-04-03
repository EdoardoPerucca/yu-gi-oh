<script>
import { store } from "./store.js";
import axios from "axios";

import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import AppSearch from "./components/AppSearch.vue";

export default {

  data() {
    return {
      store,
    }
  },
  components:
  {
    AppMain,
    AppLoader,
    AppSearch
  },

  created() {
    axios.get(this.store.APIbase).then((res) => {
      console.log(res.data.data);
      this.store.cards = res.data.data;

      this.store.loading = false;
    });
  },

  methods: {

    searchName() {
      if (this.store.cardSearch != "") {
        let newName = "&fname=" + this.store.cardSearch;

        axios.get(this.store.APIbase + newName).then((res) => {
          this.store.cards = res.data.data
        })
      } else {
        axios.get(this.store.APIbase).then((res) => {
          this.store.cards = res.data.data;
        });
      }

      this.store.cardSearch = '';
    }
  }

}
</script>

<template>
  <AppLoader v-if="store.loading"></AppLoader>

  <AppSearch @userSearch="searchName()"></AppSearch>

  <div>
    <AppMain>


    </AppMain>
  </div>
</template>

<style lang="scss" scoped></style>