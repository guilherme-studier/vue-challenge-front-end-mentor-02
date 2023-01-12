<template>
  <div class="container">
    <nav>
      <img src="../assets/logo.svg" alt="logo" />
      <div v-show="!mobileView" class="container__nav-menu">
        <ul>
          <li v-for="(link, index) in links" :key="index"><a :href="link.link">{{ link.name }}</a></li>
        </ul>
        <button class="container__nav-contact">Contact</button>
      </div>
      <a 
        v-show="mobileView && !openMenuMobile"
        @click="openMenuMobile = !openMenuMobile"
        class="container__nav-btn-open-mobile"
        :class="[openMenuMobile ? 'container__nav-btn-open-mobile-opened' : '']" 
      >
        <img src="../assets/icon-hamburger.svg" />
      </a>
      <div 
        v-show="mobileView" 
        :class="[openMenuMobile ? 'container__nav-menu-mobile-open' : '']" class="container__nav-menu-mobile"
      >
        <a 
          v-show="mobileView && openMenuMobile"
          @click="openMenuMobile = !openMenuMobile"
          class="container__nav-btn-close-mobile"
          :class="[openMenuMobile ? 'container__nav-btn-open-mobile-opened' : '']" 
        >
          <img src="../assets/icon-close-menu.svg" />
        </a>
        <ul>
          <li v-for="(link, index) in links" :key="index"><a :href="link.link">{{ link.name }}</a></li>
        </ul>
        <button class="container__nav-contact">Contact</button>
      </div>
    </nav>
    <div class="content">
      <h1>We are creatives</h1>
      <img src="../assets/icon-arrow-down.svg" alt="Flecha para baixo">
    </div>
  </div>
</template>

<script>
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
      mobileView: true,
      openMenuMobile: null,
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
  .container {
    background-image: url('../assets/desktop/image-header.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    height: 97vh;
  }

  .container nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    height: 5rem;
  }

  .container__nav-btn-open-mobile {
    z-index: 999;
    cursor: pointer;
  }

  .container__nav-btn-open-mobile img {
    width: 100%;
    border-bottom: 1px solid transparent;
    transform: rotate(0);
    transition: 1s ease all;
  }

  .container__nav-btn-open-mobile img:hover {
    transform: rotate(360deg);
  }

  .container nav .container__nav-menu {
    display: flex;
  }

  .container nav .container__nav-menu ul {
    display: flex;
    align-items: center;
    list-style: none;
    text-decoration: none;
    padding-right: 3rem;
  }

  .container nav .container__nav-menu ul li a {
    padding-left: 3rem;
    list-style: none;
    text-decoration: none;
    color: var(--white);
    font-weight: 400;
  }

    .container nav .container__nav-menu button {
    background: var(--white);
    border: none;
    border-radius: 30px;
    padding: 1rem;
    font-family: 'Fraunces', serif;
    text-transform: uppercase;
  }

  /* mobile */
  .container__nav-menu-mobile {
    display: flex;
    background: var(--white);
    height: 100%;
    width: 15rem;
    position: fixed;
    right: -15rem;
    top: 0;
    flex-direction: column;
    padding: 2rem;

    transition: 1s ease all;
  }


  .container__nav-menu-mobile-open {
    right: 0;
  }

  .container .container__nav-menu-mobile .container__nav-btn-close-mobile {
    cursor: pointer;
    position: absolute;
    right: 2rem;
  }

  .container .container__nav-menu-mobile ul {
    display: flex;
    list-style: none;
    text-decoration: none;
    flex-direction: column;
    padding-top: 3rem;
  }

  .container .container__nav-menu-mobile ul li {
    padding: 2rem;
    align-items: center;
    text-align: center;
  }

  .container .container__nav-menu-mobile ul li a {
    list-style: none;
    text-decoration: none;
    color: var(--gray-900);
    font-weight: 400;
  }

    .container .container__nav-menu-mobile button {
    background: var(--gray-900);
    color: var(--white);
    border: none;
    border-radius: 30px;
    padding: 1rem;
    font-family: 'Fraunces', serif;
    text-transform: uppercase;
    margin: 1.5rem
  }

  .container .content {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 5rem;
  }

  .container .content h1 {
    font-family: 'Fraunces', serif;
    text-transform: uppercase;
    font-weight: 600;
    font-size: 3.5rem;
    color: var(--white);
    text-align: center;
  }

  .container .content img {
    width: 3rem;
    margin: 4rem;
  }

</style>