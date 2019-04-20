<template>
  <div class="tile">
    <div class="tile-content">
      <h3>{{ title }}</h3>
      <p>{{ content }}</p>
      <i :class="icon"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Tile',
  props: {
    title: {
      type: String,
      required: true
    },
    content: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.tile {
  position: relative;
  padding: 1rem 0;
  @media screen and (min-width: 768px) {
    padding: 1rem;
  }
  &-content {
    position: relative;
    border: 1px solid #37363F;
    padding: 1rem;
  }
  h3 {
    margin-bottom: 1rem;
  }
  p {
    line-height: 1.5;
  }
  i {
    position: absolute;
    top: 1rem;
    right: 1rem;
  }
}
</style>
