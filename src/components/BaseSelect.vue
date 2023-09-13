<script>
import { store } from "../data/store";

export default {
  data() {
    return {
      store,
      selectedOption: "all",
    };
  },

  emits: ["option-change"],
};
</script>

<template>
  <div class="container py-3">
    <h4>Filter by archetype:</h4>
    <select
      @change="$emit('option-change', selectedOption)"
      v-model="selectedOption"
      class="form-select w-25"
    >
      <option value="all">All archetypes</option>
      <option
        v-for="archetype in store.archetypes"
        :value="archetype.archetype_name"
      >
        {{ archetype.archetype_name }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped></style>
