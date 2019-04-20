<template>
  <div class="main">
    <slot name="notification"/>
    <slot/>
    <slot name="footer"/>
    <slot name="newsletter"/>
  </div>
</template>

<script>
export default {
  name: 'Layout'
}
</script>

<style lang="scss" scoped>
.main {
  width: 100%;
  @media screen and (min-width: 1366px) {
    margin-right: auto;
    margin-left: auto;
    max-width: 1366px;
  }
}
</style>
