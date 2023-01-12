<template>
  <div class="banner">
    <img src="../assets/desktop/image-gallery-milkbottles.jpg" alt="img-banner-01">
    <img src="../assets/desktop/image-gallery-orange.jpg" alt="img-banner-02">
    <img src="../assets/desktop/image-gallery-cone.jpg" alt="img-banner-03">
    <img src="../assets/desktop/image-gallery-sugarcubes.jpg" alt="img-banner-04">
  </div>
</template>

<script>
export default {
  name: 'Banner',
}
</script>

<style scoped>
  .banner {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
  }

  .banner img {
    flex: 1 1 184px;
  }

  .banner img {
    height: 20rem;
    width: 1rem;
  }
</style>