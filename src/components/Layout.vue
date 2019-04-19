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

</style>
