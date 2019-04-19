<template>
  <transition name="slide">
    <div class="notification" v-if="isActive">
      <container>
        <p>By accessing and using this website, you acknowledge that you have read and understand our <a href="">Cookie Policy</a>, <a href="">Privacy Policy</a>, and our <a href="">Terms of Service</a>.</p>
        <basic-button class="notification-btn" color="#1678C2" @click.native="onButtonClick">Got it</basic-button>
      </container>
    </div>
  </transition>
</template>

<script>
import Container from '@/components/Container'
import Button from '@/components/Button'

export default {
  name: 'Notification',
  data() {
    return {
      isActive: true
    }
  },
  components: {
    Container,
    'basic-button': Button
  },
  methods: {
    onButtonClick() {
      this.isActive = false
    }
  }
}
</script>

<style lang="scss" scoped>
.notification {
  position: sticky;
  top: 0;
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

.slide-enter-active {
  transition-duration: 0.3s;
  transition-timing-function: ease-in;
}

.slide-leave-active {
  transition-duration: 0.2s;
  transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
}

.slide-enter-to, .slide-leave {
  max-height: 100vh;
  overflow: hidden;
}

.slide-enter, .slide-leave-to {
  overflow: hidden;
  max-height: 0;
}

</style>
