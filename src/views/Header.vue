<template>
  <section class="hero is-info is-small">
    <div class="hero-head">
      <nav class="navbar">
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
      <div class="container has-text-left">
          <p class="title has-text-black">
              <router-link to="/">
                <a>
                  <img class="banner-image" src="../assets/images/love-park-logo.png">
                </a>
              </router-link>
              <span class="heading-text">Spring into LOVE</span>
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
  .hero-body {
    padding: 0;
}
  p {
    display: flex;
    justify-content: start;
    align-items: end;
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
</style>