<template>
    <div class="content__cherry" :style="`background-image: url('${img}')`">
      <h1>{{ title }}</h1>
      <p>{{ subtitle }}</p>
    </div>
</template>

<script>

export default {
  name: 'Photography',
  props: {
    title: {
      type: String,
      default: null,
    },
    subtitle: {
      type: String,
      default: null
    },
    img: {
      type: String,
      default: null
    }
  }
}
</script>

<style scoped>
  .content__cherry {
    background-size: cover;
    background-repeat: no-repeat;
    background-position: bottom;
    text-align: center;
    height: 40rem;
  }

  .content__cherry h1 {
    font-size: 1.8rem;
    font-weight: 700;
    font-family: 'Fraunces', serif;
    color: var(--very-dark-desaturated-blue);
    padding: 25rem 1rem 1.5rem 1rem;
  }

  .content__cherry p {
    font-size: 1rem; 
    color: var(--very-dark-desaturated-blue);
    padding-bottom: 1rem;
    line-height: 1.5rem;
  }
</style>
