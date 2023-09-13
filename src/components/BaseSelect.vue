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
  <div class="container pt-4">
    <h4>Filter by archetype:</h4>
    <select class="form-select w-25">
      <option selected>Select an archetype...</option>
      <option v-for="archetype in store.archetypes" value="1">
        {{ archetype.archetype_name }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped></style>
