<template>
  <header class="header">
    <div class="container">
      <nav class="navbar" aria-label="main menu">
        <router-link to="about" class="menu" aria-label="menu">
          &#9776;
        </router-link>
        <router-link to="visitor-info" class="link">
          Visitor Info
        </router-link>
        <router-link to="events" class="link">
          Events
        </router-link>
        <router-link to="get-involved" class="link">
          Get Involved
        </router-link>
        <router-link to="about" class="link">
          About
        </router-link>
      </nav>
      <div class="banner">
        <router-link to="/">
          <img
            class="banner-image"
            src="../assets/images/love-park-logo.png"
            alt="love park logo"
          />
        </router-link>
        <h2 class="banner-title">Spring into LOVE</h2>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
@import "../assets/styles/variables.scss";

.header {
  background: $sky;
  padding: 0.5rem;
  padding-bottom: 2.25rem;
  width: 100%;
  display: grid;
  place-items: center;
}

.navbar {
  display: flex;
  justify-content: end;
  align-items: end;
}

.navbar a {
  color: inherit;
  text-decoration: none;
  font-weight: bold;
}

.navbar .menu {
  font-size: 1.5rem;
}

.navbar .link {
  display: none;
  min-width: max-content;
  padding: 0.5rem 2.5rem;
}

.banner {
  display: grid;
  grid-template-columns: minmax(50px, 100px) max-content;
  place-items: end start;
  grid-gap: 0.5rem;
}

.banner-image {
  width: 100%;
}

.banner-title {
  font-weight: bold;
  margin: 0;
}

.container {
  max-width: 1000px;
  width: 100%;
}

@media only screen and (min-width: 768px) {
  .header {
    padding: 0;
    padding-bottom: 2.25rem;
    padding-left: 0.5rem;
  }

  .navbar .menu {
    display: none;
  }

  .navbar .link {
    display: unset;
  }

  .navbar .router-link-active {
    background: $pavement;
    color: $snow;
  }

  .banner {
    grid-template-columns: 200px max-content;
  }
}
</style>
