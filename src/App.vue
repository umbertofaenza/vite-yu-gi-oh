<script>
import axios from "axios";
import { store } from "./data/store";

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      store,
    };
  },

  methods: {
    fetchCards(endpoint) {
      axios.get(endpoint).then((response) => {
        store.cards = response.data.data;
      });
    },
  },

  created() {
    this.fetchCards(
      "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
    );
  },
  components: { AppHeader, AppMain },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
