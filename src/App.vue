<template>
  <div id="app">
    <Layout>
      <Notification slot="notification"/>

      <Hero/>

      <Highlights/>
    </Layout>
  </div>
</template>

<script>
import Layout from '@/components/Layout'

import Notification from '@/views/Notification'
import Hero from '@/views/Hero'
import Highlights from '@/views/Highlights'

export default {
  name: 'app',
  components: {
    Layout,
    Notification,
    Hero,
    Highlights
  }
}
</script>

<style lang="scss">
@import 'https://use.fontawesome.com/releases/v5.8.1/css/all.css';

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
