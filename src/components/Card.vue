<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<template>
  <div class="col">
    <!-- card -->
    <div class="single-card">
      <!-- media -->
      <div class="card-media">
        <img :src="card.card_images[0].image_url" />
      </div>
      <!-- text -->
      <div class="card-text">
        <!-- name -->
        <span class="card-name">
          {{ card.name }}
        </span>
        <!-- archetype -->
        <span v-if="card.archetype" class="card-acrhetype">
          {{ card.archetype }}
        </span>
        <!-- if no archetype, print race -->
        <span v-if="!card.archetype" class="card-race">
          {{ card.race }}
        </span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.single-card {
  background-color: #d48f38;
  text-align: center;
  min-height: 450px;

  .card-name,
  .card-archetype {
    display: block;
  }

  .card-name {
    color: #fff;
    text-transform: uppercase;
    font-weight: bold;
    padding: 10px 0;
  }
}
</style>
