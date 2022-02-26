<template>
    <div class="home">
      <Header></Header>
    </div>

    <div class="container content-align is-overlay">
        <figure class="image">
          <img src="../assets/images/love-park-hero.jpeg">
        </figure>
    </div>

    <div class="footer-div">
      <Footer></Footer>
    </div>

</template>

<script>
  import Header from '@/views/Header.vue'
  import Footer from '@/components/Footer.vue'

  export default {
    name: 'About',
    components: {
        Header,
        Footer
    }
  }
</script>

<style scoped>
  * {
    overflow: hidden;
  }
  .hero.is-info .title {
      color: black;
  }
  .navbar-end {
      color: black;
  }
  .hero.is-info {
      width: 100vw;
      background-color: #b3e8f9;
      color: #fff;
  }
  .top-padding {
      padding-top: 20px;
  }
</style>
