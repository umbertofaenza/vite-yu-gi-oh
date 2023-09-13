<script>
import { store } from "../data/store";

export default {
  data() {
    return {
      store,
      selectedOption: "default",
    };
  },

  emits: ["option-change"],
};
</script>

<template>
  <div class="container pt-4">
    <h4>Filter by archetype:</h4>
    <select
      @change="$emit('option-change', selectedOption)"
      v-model="selectedOption"
      class="form-select w-25"
    >
      <option value="default">Select an archetype...</option>
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
