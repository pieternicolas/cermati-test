<template>
  <div class="notification">
    <container>
      <p>By accessing and using this website, you acknowledge that you have read and understand our <a href="">Cookie Policy</a>, <a href="">Privacy Policy</a>, and our <a href="">Terms of Service</a>.</p>
      <basic-button class="notification-btn" color="#1678C2">Got it</basic-button>
    </container>
  </div>
</template>

<script>
import Container from '@/components/Container'
import Button from '@/components/Button'

export default {
  components: {
    Container,
    'basic-button': Button
  }
}
</script>

<style lang="scss" scoped>
.notification {
  width: 100%;
  background-color: #F1F1F1;
  .container {
    padding: 1em 0;
    @media (min-width: 768px) {
      max-width: 720px;
    }
  }
  p {
    @media (min-width: 768px) {
      flex-basis: 90%;
    }
  }
  &-btn {
    margin-top: 0.5em;
    @media (min-width: 768px) {
      margin-top: 0;
    }
  }
}
</style>
