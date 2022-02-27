<template>
  <main class="about view">
    <Header />
    <div class="container">
      <h1>About</h1>
      <div class="text-container" v-if="data" v-html="data.content" />
    </div>
    <figure class="image-container">
      <img
        src="../assets/images/parks-and-rec-logo.png"
        alt="philadelphia parks and recreation banner"
      />
    </figure>
    <Footer />
  </main>
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
  methods: {
    getData: function() {
      fetch(
        "https://locations-staging-admin.phila.gov/love-park/wp-json/pages/v2/archive?id=7"
      )
        .then((res) => res.json())
        .then((data) => (this.data = data))
        .catch((err) => console.log(err.message));
    },
  },
  mounted() {
    this.getData();
  },
  data() {
    return {
      data: null,
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/styles/variables.scss";
.about /deep/ .header {
  background: $sun;
}

.container {
  padding: 1rem;
  background: $snow;
  margin-top: -2rem;
  max-width: 1000px;
}

.footer {
  background: $ocean;
  color: $snow;
}

.footer /deep/ a {
  color: $snow;
}

.image-container {
  display: grid;
  place-items: center;
  padding: 1rem;
  padding-top: 5rem;
}

.image-container img {
  width: 100%;
}
</style>
