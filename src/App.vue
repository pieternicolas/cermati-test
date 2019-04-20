<template>
  <div id="app">
    <layout>
      <notification slot="notification"/>
      <hero/>
      <highlights/>
      <page-footer slot="footer"/>
      <newsletter slot="newsletter"/>
    </layout>
  </div>
</template>

<script>
import Layout from '@/components/Layout'

import Notification from '@/views/Notification'
import Hero from '@/views/Hero'
import Highlights from '@/views/Highlights'
import PageFooter from '@/views/PageFooter'
import Newsletter from '@/views/Newsletter'

export default {
  name: 'app',
  components: {
    Layout,
    Notification,
    Hero,
    Highlights,
    PageFooter,
    Newsletter
  },
  created() {
    document.title = `​${this.$name} | Cermati.com Front-end Developer Entry Test`
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
