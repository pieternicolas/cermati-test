<template>
  <transition name="slide">
    <div class="newsletter" v-if="isShown">
      <h2>Get latest updates in web technologies</h2>
      <p>I write articles related to web technologies, such as design trends, development tools, UI/UX case studies and reviews, and more. Sign up to my newsletter to get them all.</p>
      <span class="close" @click="closePanel">x</span>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'Newsletter',
  data() {
    return {
      scrollPastThird: false,
      closedAt: ''
    }
  },
  computed: {
    isShown() {
      if (!this.closedAt && this.scrollPastThird) {
        return true
      }

      if (this.closedAt) {
        return new Date() > new Date(new Date(this.closedAt).getTime() + 10 * 60000)
      }

      return false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.toggleInitialPanel)
    this.closedAt = localStorage.getItem('hideNewsletterAt') ? new Date(localStorage.getItem('hideNewsletterAt')) : ''
  },
  methods: {
    toggleInitialPanel() {
      if (window.pageYOffset >= window.innerHeight / 3) {
        this.scrollPastThird = true
      }
    },
    closePanel() {
      localStorage.setItem('hideNewsletterAt', new Date())
      this.closedAt = new Date()
      window.removeEventListener('scroll', this.toggleInitialPanel)
    }
  }
}
</script>


<style lang="scss" scoped>
.newsletter {
  position: fixed;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 123, 191, 0.8);
  color: #ffffff;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  padding: 1.5rem 1rem;
  max-width: 640px;
  h2 {
    margin-bottom: 0.5rem;
  }
  p {
    line-height: 1.5;
  }
}

.close {
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  &:hover {
    cursor: pointer;
  }
}

.slide-enter-active {
  transition-duration: 0.8s;
  transition-timing-function: ease-in;
}

.slide-leave-active {
  transition-duration: 0.8s;
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
