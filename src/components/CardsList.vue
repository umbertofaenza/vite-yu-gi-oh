<script>
import axios from "axios";

import Card from "./Card.vue";

export default {
  data() {
    return {
      cards: [],
    };
  },

  components: { Card },

  methods: {
    fetchCards(endpoint) {
      axios.get(endpoint).then((response) => {
        this.cards = response.data.data;
      });
    },
  },

  created() {
    this.fetchCards(
      "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
    );
  },
};
</script>

<template>
  <div class="container py-5">
    <div class="row p-4 g-3 row-cols-2 row-cols-md-3 row-cols-lg-5">
      <Card v-for="card in cards" :key="card.id" :card="card" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.row {
  background-color: #fff;
}
</style>
