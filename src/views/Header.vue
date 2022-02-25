<template>
  <section class="hero is-info is-small">
    <div class="hero-head">
      <nav class="navbar">
        <router-link to="about">
                  &#9776;
              </router-link>
        <div class="container">
          <div id="" class="navbar-menu">
            <div class="navbar-end has-text-black">
              <router-link to="about">
                  About
              </router-link>
            </div>
          </div>
      </div>
    </nav>
  </div>
  <div class="hero-body">
      <div class="container-two has-text-left">
          <p class="title has-text-black">
              <router-link to="/">
                <a>
                  <img class="banner-image" src="../assets/images/love-park-logo.png">
                </a>
              </router-link>
<<<<<<< Updated upstream
              <span class="heading-text">Spring into LOVE</span>
=======
              <span class="heading">Spring into LOVE</span>
>>>>>>> Stashed changes
          </p>
      </div>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'Header',
  }
</script>

<style scoped>
<<<<<<< Updated upstream
  .hero-body {
    padding: 0;
}
  p {
    display: flex;
    justify-content: start;
    align-items: end;
=======
  .navbar {
    text-align: right;
    font-size: 1.25rem;
    color: #444444;
  }
  .hero-head {
    height: 2.5rem;
  }
  .banner-image {
    height: 30vw;
>>>>>>> Stashed changes
    padding-bottom: 25px;
}
  .banner-image {
    width: 60vw;
  }
  .heading-text {
    font-size: 1.5rem;
    font-weight: bold;
    width: 150vw;
    color: #444444;
    text-align: left;
  }
  .title {
    display: flex;
    justify-content: start;
    align-items: end;
  }

  .heading {
    color: #444444;
    font-size: 5vw;
    font-weight: bold;
    width: 60vw;
    padding-bottom: 1rem;
  }
</style>