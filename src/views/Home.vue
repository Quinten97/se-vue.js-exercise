<template>
  <main class="home view">
    <div class="container">
      <Header />
      <figure class="image-container">
        <img src="../assets/images/love-park-hero.jpeg" />
      </figure>
    </div>
  </main>
  <Footer />
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "About",
  components: {
    Header,
    Footer,
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/variables.scss";
.container {
  width: 100%;
  display: grid;
  place-items: center;
}
.image-container {
  padding: 1rem;
  background: $snow;
  margin-top: -2rem;
  max-width: 1000px;
}

.image-container img {
  width: 100%;
}

/deep/ .column {
  border-color: rgba($pavement, 0.5);
}
</style>
