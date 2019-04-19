<template>
  <div class="container">
    <div class="content">
      <slot/>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  width: 100%;
  margin-right: auto;
  margin-left: auto;
  .content {
    display: flex;
    flex-wrap: wrap;
    margin: 0 0.5em;
  }
}
</style>
