<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<template>
  <div class="col single-card">
    {{ card.name }}
  </div>
</template>

<style lang="scss" scoped></style>
