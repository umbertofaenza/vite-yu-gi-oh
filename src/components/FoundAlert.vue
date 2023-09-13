<script>
import { store } from "../data/store";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <div class="alert alert-success" role="alert">
      Results: {{ store.cards.length }}
    </div>
  </div>
</template>

<style lang="scss" scoped>
.alert {
  width: max-content;
}
</style>
