<template>
  <footer class="footer">
    <div class="columns">
      <section class="column" v-if="data">
        <strong>Address</strong>
        <p>{{ data.address.address_1 }}</p>
        <p>
          {{ data.address.city }} {{ data.address.state }}
          {{ data.address.zip }}
        </p>
        <a href="{{data.address.map_url}}">Map</a>
      </section>
      <section class="column" v-if="data">
        <strong>Hours</strong>
        <p>{{ todaysHours().start_time }} - {{ todaysHours().end_time }}</p>
        <a href="">See all hours</a>
      </section>
      <section class="column" v-if="data">
        <strong>Contact</strong>
        <p>
          <a href="{{data.contact.email}}">{{ data.contact.email }}</a>
        </p>
        <p>
          <a href="{{data.contact.phone}}">{{ data.contact.phone }}</a>
        </p>
        <div class="icons">
          <a
            class="icon"
            href="{{data.contact.facebook}}"
            aria-label="facebook link"
            ><font-awesome-icon :icon="['fab', 'facebook']"
          /></a>
          <a
            class="icon"
            href="{{data.contact.twitter}}"
            aria-label="twitter link"
            ><font-awesome-icon :icon="['fab', 'twitter']" class="icon alt"
          /></a>
          <a
            class="icon"
            href="{{data.contact.insta}}"
            aria-label="insatagram link"
            ><font-awesome-icon :icon="['fab', 'instagram']" class="icon alt"
          /></a>
        </div>
      </section>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  mounted() {
    this.getData();
  },
  methods: {
    getData: function() {
      fetch(
        "https://locations-staging-admin.phila.gov/love-park/wp-json/locations/v1/connect"
      )
        .then((res) => res.json())
        .then((data) => (this.data = data))
        .catch((err) => console.log(err.message));
    },
    todaysHours: function() {
      const d = new Date();
      let day = d.getDay();

      if (day === 0) {
        return this.data.hours.sunday;
      } else if (day === 1) {
        return this.data.hours.monday;
      } else if (day === 2) {
        return this.data.hours.tuesday;
      } else if (day === 3) {
        return this.data.hours.wednesday;
      } else if (day === 4) {
        return this.data.hours.thursday;
      } else if (day === 5) {
        return this.data.hours.friday;
      } else if (day === 6) {
        return this.data.hours.saturday;
      }
    },
  },
  data() {
    return {
      data: null,
    };
  },
  created() {},
};
</script>

<style scoped lang="scss">
@import "../assets/styles/variables.scss";

.footer {
  width: 100%;
  padding: 1rem;
  display: grid;
  place-items: center;
}

.footer :last-child {
  border: none;
}

.columns {
  max-width: 1000px;
  width: 100%;
}

.column {
  padding: 1rem;
  border-bottom: 1px solid rgba($sunset, 0.5);
}

.icons > a {
  margin: 0.25rem;
}

@media only screen and (min-width: 768px) {
  .columns {
    display: flex;
    justify-content: center;
  }

  .column {
    width: calc(100% / 3);
    border: none;
    border-right: 1px solid rgba($sunset, 0.5);
    margin: 1rem;
    padding: 1rem;
  }
}
</style>
