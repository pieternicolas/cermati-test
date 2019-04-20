<template>
  <container>
    <footer>
      © {{ new Date().getFullYear() }} {{ $name }}. All rights reserved.
    </footer>
  </container>
</template>

<script>
import Container from '@/components/Container'

export default {
  name: 'PageFooter',
  components: {
    Container
  }
}
</script>

<style lang="scss" scoped>
.container {
  background-color: #050225;
}
footer {
  width: 100%;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  color: #ffffff;
  padding: 2rem 0;
  text-align: center;
}
</style>
