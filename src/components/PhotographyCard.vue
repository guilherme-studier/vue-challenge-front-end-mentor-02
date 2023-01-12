<template>
  <div class="content">
    <Photography
      title="Graphic Design"
      subtitle="Great design makes you memorable. We deliver artwork that underscores your brand message and captures potential clients attention."
      :img="cherry"
    />
    <Photography
      title="Photography"
      subtitle="Increase your credibility by getting the most stunning, high-quality photos that improve your business image."
      :img="orange"
    />
  </div>
</template>

<script>
import Photography from '../components/Photography.vue';

import ImgCherry from '../assets/desktop/image-graphic-design.jpg';
import ImgOrange from '../assets/desktop/image-photography.jpg';

export default {
  name: 'PhotographyCard',
  data() {
    return {
      cherry: ImgCherry,
      orange: ImgOrange
    }
  },
  components: {
    Photography,
  },
}
</script>

<style scoped>
.content {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
  }

  .content > div {
    flex: 1 1 400px;
    padding: 0 12rem;
    width: 100%;
  }

  @media (max-width: 1050px) {
    .content > div {
      padding: 0 5rem;
    }
  }
</style>