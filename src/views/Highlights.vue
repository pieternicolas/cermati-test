<template>
  <container>
    <div class="highlights">
      <div class="header">
        <h1>How Can I Help You?</h1>
        <p>Our work then targeted, best practices outcomes social innovation synergy. Venture philanthropy, revolutionary inclusive policymaker relief. User-centered program areas scale.</p>
      </div>
      <div class="tiles">
        <template v-for="item in highlightsData">
          <tile :key="item.title" :title="item.title" :content="item.content" :icon="item.icon"/>
        </template>
      </div>
    </div>
  </container>
</template>

<script>
import Container from '@/components/Container'
import Tile from '@/components/Tile'

import highlightsData from '@/assets/data/highlightsData'

export default {
  name: "Highlights",
  components: {
    Container,
    Tile
  },
  data() {
    return {
      highlightsData
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  background-color: #E5E5E5;
  color: #37363F;
}
h1, p {
  text-align: center;
  margin-bottom: 1rem;
}
.highlights {
  width: 100%;
  padding: 3em 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.header {
  @media (min-width: 768px) {
    max-width: 60%;
  }
}
.tiles {
  display: grid;
  grid-template-columns: 100%;
  @media screen and (min-width: 480px) and (max-width: 960px) {
    grid-template-columns: repeat(2, 1fr);
  }
  @media screen and (min-width: 960px) {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
