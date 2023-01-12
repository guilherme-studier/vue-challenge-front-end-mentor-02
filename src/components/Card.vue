<template>
  <div class="content-brand" :style="row && !mobileView ? `flex-direction: ${row}`  : ''">
    <div class="content-brand__text">
      <h1>{{ title }}</h1>
      <p>{{ subtitle }}</p>
      <h2>Learn More</h2>
    </div>
    <div class="content-brand__img">
      <img :src="img" alt="">
    </div>
  </div>
</template>

<script>

export default {
  name: 'Card',
  data() {
    return {
      mobileView: true,
    }
  },
  props: {
    title: {
      type: String,
      default: null,
    },
    subtitle: {
      type: String,
      default: null,
    },
    img: {
      type: String, 
      default: null
    },
    row: {
      type: String,
      default: null
    }
  },
  created() {
    window.addEventListener('resize', this.checkMobileView);
    this.checkMobileView();
  },
  methods: {
    checkMobileView() {
      if (window.innerWidth <= 750) return this.mobileView = true;
      else return this.mobileView = false;
    }
  }
}
</script>

<style scoped>
  .content-brand {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    margin: 0 auto;
  }

  .content-brand > div {
    flex: 1 1 350px;
    width: 100%;
  }

  .content-brand .content-brand__text {
    width: 100%;
    padding: 10rem;
  }

  @media (max-width: 1050px) {
    .content-brand {
      flex-direction: column-reverse;
    }
    .content-brand .content-brand__text {
      display: flex;
      text-align: center;
      flex-direction: column;

      padding: 4rem 3rem;
    }
  }

  .content-brand .content-brand__img img {
    width: 100%;
    height: 100%;  
    background-size: cover;
  }

  .content-brand .content-brand__text h1 {
    font-family: 'Fraunces', serif;
    font-weight: 600;
    font-size: 2.5rem;
  }

  .content-brand .content-brand__text p {
    font-size: 1rem;
    padding: 2rem 0;
    color: var(--dark-grayish-blue);
  }

  .content-brand .content-brand__text h2 {
    font-family: 'Fraunces', serif;
    font-weight: 800;
    font-size: 0.9rem;
    text-transform: uppercase;
  }
</style>
