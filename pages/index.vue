<template>
  <section class="reservations">
    <h3>Find your reservations</h3>
    <div class="field">
      <p class="control">
        <span class="select">
          <select>
            <option>Hotel California</option>
            <option>Hotel Miami</option>
          </select>
        </span>
      </p>
    </div>
    <Reservation
      thumbnail="https://cdn.pixabay.com/photo/2016/10/25/12/28/los-angeles-1768743_960_720.jpg"
      title="Hotel California"
      preview="You can checkout anytime you like, but you can never leave"
    />
    <Reservation
      thumbnail="https://cdn.pixabay.com/photo/2016/01/19/18/00/city-1150026_960_720.jpg"
      title="Hotel Miami"
      preview="All night, on the beach, till the break of dawn"
    />
    <div class="container">
      <div class="columns is-multiline">
        <div
          v-for="(reservation, confirmationCode) in reservations"
          :key="confirmationCode"
          class="column is-one-quarter"
        >
          <a :href="reservation.url" target="_blank">
            <div class="card">
              <div class="card-image">
                <figure class="image is-3by2">
                  <img :src="reservation.cityImage" :alt="reservation.city">
                </figure>
              </div>
              <div class="card-content">
                <div class="content">{{ reservation.city }}</div>
              </div>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Reservation from '@/components/Reservation'

export default {
  components: {
    Reservation
  },
  async asyncData ({ app, $axios }) {
    const { reservations } = await app.$axios.$get(
      'https://demo6894002.mockable.io/akasa-data'
    )
    // eslint-disable-next-line no-console
    console.log({ reservations })
    return { reservations }
  },
  data: () => {
    return {
      reservations: []
    }
  }
}
</script>

<style scoped>
.reservations {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}
</style>
