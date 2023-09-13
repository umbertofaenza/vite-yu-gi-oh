<script>
import axios from "axios";
import { store } from "./data/store";

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import BaseSelect from "./components/BaseSelect.vue";

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

    fetchArchetypes(endpoint) {
      axios.get(endpoint).then((response) => {
        store.archetypes = response.data;
      });
    },

    filterByArchetype(value) {
      const fullUrl = `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=${value}`;
      this.fetchCards(fullUrl);
    },
  },

  created() {
    this.fetchCards(
      "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
    );

    this.fetchArchetypes("https://db.ygoprodeck.com/api/v7/archetypes.php");
  },
  components: { AppHeader, AppMain, BaseSelect },
};
</script>

<template>
  <AppHeader />
  <BaseSelect @option-change="filterByArchetype" />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
