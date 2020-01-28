<template>
  <div>
    <!--<div class="podlogka"><img src="~/static/podlogka2.png" alt=""></div>-->
    <Banner/>
    <Navigation/>
    <Nuxt/>
    <Footer/>
  </div>
</template>

<script>
  import Banner from '~/components/Banner.vue';
  import Navigation from '~/components/Navigation.vue';
  import Navbar from '~/components/Navbar.vue';
  import Footer from '~/components/Footer.vue';

  export default {
    components: {
      Banner,
      Navigation,
      Navbar,
      Footer
    }
  }
</script>

<style lang="scss" scoped>
  .podlogka {
    display: flex;
    justify-content: center;
    position: absolute;
    width: 100%;
    opacity: .4;
  }
</style>
