<template>
  <section class="reservations">
    <h1>Reservations</h1>
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
  </section>
</template>

<script>
import Reservation from '@/components/Reservation'

export default {
  components: {
    Reservation
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
