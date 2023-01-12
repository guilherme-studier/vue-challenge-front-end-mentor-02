<template>
  <div class="section-testimonials">
      <h1>Client Testimonials</h1>
    <div class="content-testimonials">
      <Testimonial 
        :img="emilyPhoto"
        description="We put our trust in Sunnyside and they delivered, making sure our needs were met and deadlines were always hit."
        name="Emily R."
        job="Marketing Director"
      />
      <Testimonial 
        :img="thomasPhoto"
        description="Sunnysides enthusiasm coupled with their keen interest in our brands success made it a satisfying and enjoyable experience."
        name="Thomas S."
        job="Chief Operating Officer"
      />
      <Testimonial 
        :img="jenniePhoto"
        description="Incredible end result! Our sales increased over 400% when we worked with Sunnyside. Highly recommended!"
        name="Jennie F."
        job="Business Owner"
      />
    </div>
  </div>
</template>

<script>
import Testimonial from './Testimonial.vue';

import EmilyPhoto from '../assets/image-emily.jpg';
import ThomasPhoto from '../assets/image-thomas.jpg';
import JenniePhoto from '../assets/image-jennie.jpg';

export default {
  name: 'Testimonials',  
  data() {
    return {
      emilyPhoto: EmilyPhoto,
      jenniePhoto: JenniePhoto,
      thomasPhoto: ThomasPhoto,
    }
  },
  components: { 
    Testimonial
  },
}
</script>

<style scoped>
  .section-testimonials {
    width: 100%;
    display: flex;
    flex-direction: column;
    margin: 7rem 0;
  }

  .section-testimonials h1 {
    font-family: 'Fraunces', serif;
    text-transform: uppercase;
    font-size: 1.5rem;
    color: var(--grayish-blue);
    text-align: center;
  }

  .content-testimonials {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    max-width: 100%;
  }

  .content-testimonials > div {
    flex: 1 1 500px;
  }
</style>