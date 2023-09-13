<script>
import CardsList from "./CardsList.vue";
import BaseSelect from "./BaseSelect.vue";

export default {
  components: { CardsList, BaseSelect },
};
</script>

<template>
  <main>
    <BaseSelect />
    <CardsList />
  </main>
</template>

<style lang="scss" scoped>
main {
  background-color: #d48f38;
}
</style>
