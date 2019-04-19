<template>
  <div id="app">
    <Layout>
      <Notification slot="notification"/>
    </Layout>
  </div>
</template>

<script>
import Layout from '@/components/Layout'

import Notification from '@/views/Notification'

export default {
  name: 'app',
  components: {
    Layout,
    Notification
  }
}
</script>

<style lang="scss">
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
}

h1, h2, h3, h4, h5, p {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
</style>
