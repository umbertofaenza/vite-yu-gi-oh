<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<template>
  <!-- card -->
  <div class="col single-card">
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
</template>

<style lang="scss" scoped>
.single-card {
  margin-bottom: 10px;
}

.card-name,
.card-archetype {
  display: block;
}
</style>
