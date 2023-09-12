<script>
import CardsList from "./CardsList.vue";

export default {
  components: { CardsList },
};
</script>

<template>
  <main>
    <div class="container">
      <CardsList />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  height: 100vh;
  background-color: #d48f38;
}
</style>
