<script>
import { store } from "../data/store";
import Card from "./Card.vue";
import FoundAlert from "./FoundAlert.vue";

export default {
  data() {
    return {
      store,
    };
  },

  components: { Card, FoundAlert },
};
</script>

<template>
  <div class="container py-5">
    <FoundAlert />
    <div class="row mt-3 p-4 g-3 row-cols-2 row-cols-md-3 row-cols-lg-5">
      <Card v-for="card in store.cards" :key="card.id" :card="card" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.row {
  background-color: #fff;
}
</style>
