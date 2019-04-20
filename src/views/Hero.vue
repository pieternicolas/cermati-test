<template>
  <div class="hero">
    <img src="@/assets/img/y-logo-white.png" alt="" class="logo">
    <container>
      <div class="hero-content">
        <h1>Hello! I'm {{ $name }}</h1>
        <h2>Consult, Design, and Develop Websites</h2>
        <h4>
          Have something great in mind? Feel free to contact me. <br>
          I'll help you to make it happen.
        </h4>
        <basic-button :outline="true" class="hero-button">
          LET'S MAKE CONTACT
        </basic-button>
      </div>
    </container>
  </div>
</template>

<script>
import Container from '@/components/Container'
import Button from '@/components/Button'

export default {
  name: 'Hero',
  components: {
    Container,
    'basic-button': Button
  }
}
</script>

<style lang="scss" scoped>
.hero {
  display: flex;
  flex-direction: column;
  position: relative;
  width: 100%;
  min-height: 100vh;
  background-image: linear-gradient(rgba(0, 74, 117, 0.7), rgba(0, 74, 117, 0.7)),
                    url('~@/assets/img/work-desk__dustin-lee.jpg');
  background-size: cover;
  .logo {
    position: absolute;
    z-index: 2;
    width: 50px;
    top: 1em;
    left: 1em;
    @media (min-width: 768px) {
      top: 2em;
      left: 3em;
    }
  }
}
.container {
  display: flex;
  flex: 1;
  justify-content: center;
  align-items: center;
  min-height: 100%;
  height: 100%;
  padding: 1em 0;
  color: #ffffff;
  @media (min-width: 768px) {
    max-width: 720px;
  }
  .hero-content {
    margin: 0 auto;
    padding: 0 1em;
    text-align: center;
  }
  h1, h2, h4 {
    margin-bottom: 0.5em;
  }
  h1 {
    font-weight: 300;
  }
  h4 {
    font-weight: 100;
    line-height: 1.5;
  }
  .hero-button {
    margin-top: 1.5em;
    padding: 0.75rem 1.5rem;
  }
}
</style>
