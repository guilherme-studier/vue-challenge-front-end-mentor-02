<template>
  <Header />
  <Card 
    title="Transform your brand" 
    subtitle="We are a full-service creative agency specializing in helping brands grow fast. Engage your clients through compelling visuals that do most of the marketing for you." 
    :img="eggImg" 
  />
  <Card 
    title="Stand out to the right audience" 
    subtitle="Using a collaborative formula of designers, researchers, photographers, videographers, and copywriters, well build and extend your brand in digital places." 
    :img="glassImg"
    row="row-reverse"
  />
  <PhotographyCard />
  <Testimonials />
  <Banner />
  <footer>
    <div class="menu-footer-title">
      <h1>sunnyside</h1>
    </div>
    <div class="menu-footer-nav">
      <ul>
        <li v-for="(link, index) in links" :key="index"><a :href="link.link">{{ link.name }}</a></li>
      </ul>
    </div>
    <div class="menu-footer-social">
      <ul>
        <li><img src="../assets/icon-facebook.svg" alt="icon-facebook"></li>
        <li><img src="../assets/icon-instagram.svg" alt="icon-facebook"></li>
        <li><img src="../assets/icon-twitter.svg" alt="icon-facebook"></li>
      <li><img src="../assets/icon-pinterest.svg" alt="icon-facebook"></li>
      </ul>
    </div>
  </footer>
</template>

<script>
import Header from '../components/Header.vue';
import Card from '../components/Card.vue';
import PhotographyCard from '../components/PhotographyCard.vue';
import Testimonials from '../components/Testimonials.vue';
import Banner from '../components/Banner.vue';

import ImgTransform from '../assets/desktop/image-transform.jpg';
import ImgStandOut from '../assets/desktop/image-stand-out.jpg';

export default {
  name: 'Home',
  data() {
    return {
      links: [
        {
          name: 'About',
          link: '/'
        },
        {
          name: 'Services',
          link: '/'
        },
        {
          name: 'Projects',
          link: '/'
        }
      ],
      eggImg: ImgTransform,
      glassImg: ImgStandOut,
    }
  },
  components: {
    Header,
    Card,
    PhotographyCard,
    Testimonials,
    Banner
  },
}
</script>

<style scoped>
  footer {
    background-color: var(--dark-light-cyan);

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;

    padding: 2.5rem 5rem;
    width: 100%;
  }

  footer .menu-footer-title {
    padding: 1rem 5rem 3rem 5rem;
  }

  footer .menu-footer-title h1 {
    font-family: 'Fraunces', serif;
    color: var(--dark-desaturated-cyan);
    font-weight: 800;
    font-size: 2rem;
  }

  footer .menu-footer-nav > ul {
    display: flex;
    list-style: none;
    align-items: center;
    text-decoration: none;

    padding-bottom: 4rem;
  }

  footer .menu-footer-nav > ul li a {
    padding-left: 3rem;
    color: var(--dark-desaturated-cyan);
    text-decoration: none;
    list-style: none;
    font-weight: 400;
  }

  footer .menu-footer-social > ul {
    display: flex;
  }

  footer .menu-footer-social > ul li {
    list-style: none;
    padding-left: 1.5rem;
  }
</style>
