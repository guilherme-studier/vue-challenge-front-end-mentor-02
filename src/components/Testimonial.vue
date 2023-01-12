<template>
  <div class="content-testimonials__testimonial">
    <img :src="img" alt="photo">
    <p>{{ description }}</p>
    <h2>{{ name }}</h2>
    <h3>{{ job }}</h3>
  </div>
</template>

<script>
export default {
  name: 'Testimonial',
  props: {
    img: {
      type: String,
      default: null
    },
    description: {
      type: String,
      default: null
    },
    name: {
      type: String,
      default: null,
    },
    job: {
      type: String,
      default: null,
    }
  }
}
</script>

<style scoped>
  .content-testimonials__testimonial {
    padding: 5rem;
    width: 100%;
    align-items: center;
    display: flex;
    flex-direction: column;
    text-align: center;
  }

  .content-testimonials__testimonial img {
    border-radius: 50%;
    margin-bottom: 3.5rem;
    width: 7rem ;
  }

  .content-testimonials__testimonial p {
    margin-bottom: 3rem;
    color: var(--very-dark-grayish-blue);
  }

  .content-testimonials__testimonial > h2 {
    font-family: 'Fraunces', serif;
    color: var(--very-dark-desaturated-blue);
    margin-bottom: 1rem;
  }

  .content-testimonials__testimonial h3 {
    color: var(--grayish-blue);
  }
</style>