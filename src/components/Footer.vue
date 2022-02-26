<template>
  <div>
    <div class="columns">
      <div class="column" v-if="data">
        Address
        <p>{{data.address.address_1}}</p>
        <p>{{data.address.city}} {{data.address.state}} {{data.address.zip}}</p>
        <a href={{data.address.map_url}}>Map</a>
      </div>
      <div class="column" v-if="data">
        Hours
        <p>{{todaysHours().start_time}} - {{todaysHours().end_time}}</p>
        <a href="">See all hours</a>
      </div>
      <div class="column" v-if="data">
        Contact
        <p><a href={{data.contact.email}}>{{data.contact.email}}</a></p>
        <p><a href={{data.contact.phone}}>{{data.contact.phone}}</a></p>
        <div class="icons">
          <a href={{data.contact.facebook}}><font-awesome-icon :icon="['fab', 'facebook']" class="icon alt"/></a>
          <a class="icon-children" href={{data.contact.twitter}}><font-awesome-icon :icon="['fab', 'twitter']" class="icon alt"/></a>
          <a class="icon-children" href={{data.contact.insta}}><font-awesome-icon :icon="['fab', 'instagram']" class="icon alt"/></a>
        </div>
      </div>
      </div>
  </div>
</template>

<script>
  export default {
    name: 'Footer',
    mounted() {
      this.getData();
    },
    methods: {
      getData: function() {
         fetch('https://locations-staging-admin.phila.gov/love-park/wp-json/locations/v1/connect')
        .then(res => res.json())
        .then(data => this.data = data)
        .catch(err => console.log(err.message))
      },
      todaysHours: function() {
        const d = new Date();
        let day = d.getDay();

          if (day === 0) {
            return this.data.hours.sunday
          } else if (day === 1) {
            return this.data.hours.monday
          } else if (day === 2) {
            return this.data.hours.tuesday
          } else if (day === 3) {
            return this.data.hours.wednesday
          } else if (day === 4) {
            return this.data.hours.thursday
          } else if (day === 5) {
            return this.data.hours.friday
          } else if (day === 6) {
            return this.data.hours.saturday
          }

        }
      },
    data() {
      return {
        data: null
      }
    },
    created() {}
  }
</script>

<style scoped>
  a {
    text-decoration: underline;
  }
  p {
    font-weight: normal;
  }
  .columns {
    max-width: 100vw;
  }
  .column {
    padding-left: 1.5rem;
    font-weight: bold;
    font-size: 2.5vh;
    border-bottom: 1px solid #444444;
  }
  .icon-children {
    margin-left: 0.25rem;
  }

</style>
