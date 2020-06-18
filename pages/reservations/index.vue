<template>
  <section class="reservations">
    <h1>Reservations</h1>
    <Reservation
      v-for="reservation in reservations"
      :key="reservation.confirmationCode"
      :city-image="reservation.cityImage"
      :city="reservation.city"
      :confirmation-code="reservation.confirmationCode"
      :rating="reservation.rating"
    />
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
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
