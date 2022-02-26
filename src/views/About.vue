<template>
    <div class="about">
        <Header></Header>
        <div class="container content-align is-overlay">
          <h2>About</h2>
          <p v-if="data" v-html='data.content'></p>
        </div>
        <div class="columns">
            <div class="column is-one-quarter is-offset-4">
                <figure class="image">
                    <img src="../assets/images/parks-and-rec-logo.png">
                </figure>
            </div>
        </div>
        <div class="has-background-link">
            <div class="container">
                <Footer bgcolor="has-background-link" textcolor="has-text-white"></Footer>
            </div>
        </div>
    </div>
</template>

<script>
import Header from "@/views/Header.vue"
import Footer from "@/components/Footer.vue"

export default {
  name: "About",
  components: {
    Header, 
    Footer
  },
  methods: {
      getData: function() {
         fetch('https://locations-staging-admin.phila.gov/love-park/wp-json/pages/v2/archive?id=7')
        .then(res => res.json())
        .then(data => this.data = data)
        .catch(err => console.log(err.message))
      }
    },
    mounted(){
        this.getData();
    },
  data() {
      return {
          data: null
      }
  }
}
</script>

<style scoped>
    .column {
        max-width: 100vw;
    }
</style>