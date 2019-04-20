<template>
  <transition name="slide">
    <div class="newsletter-container">
      <div class="newsletter" v-if="isShown">
        <h2>Get latest updates in web technologies</h2>
        <p>I write articles related to web technologies, such as design trends, development tools, UI/UX case studies and reviews, and more. Sign up to my newsletter to get them all.</p>
        <span class="close" @click="closePanel">x</span>
        <form class="inline-form" @submit.prevent="closePanel">
          <input type="email" class="input-form" placeholder="Email address">
          <basic-button :color="'#ff8000'" @click.native="closePanel" class="submit-button">Count me in!</basic-button>
        </form>
      </div>
    </div>
  </transition>
</template>

<script>
import Button from '@/components/Button'

export default {
  name: 'Newsletter',
  components: {
    'basic-button': Button
  },
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
.newsletter-container {
  position: relative;
  clear: both;
}

.newsletter {
  position: fixed;
  bottom: 0;
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

.inline-form {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  align-items: stretch;
  margin-top: 1rem;
  .input-form {
    flex: 1 1 auto;
    position: relative;
    border-radius: 4px;
    border: 1px solid #ffffff;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    padding: 0.4rem 0.5rem;
    margin-right: 1rem;
  }
  @media screen and (max-width: 639.99px) {
    .input-form {
      width: 100%;
      margin-right: 0;
    }
    .submit-button {
      width: 100%;
      margin-top: 0.5em;
    }
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
