<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },

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
    <div class="row p-4 row-cols-2 row-cols-md-3 row-cols-lg-5">
      <div class="col single-card">
        <h1>TEST</h1>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.row {
  background-color: #fff;
}
</style>
