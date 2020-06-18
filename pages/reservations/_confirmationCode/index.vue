<template>
  <section class="single-reservation">
    <h1>{{ $route.params.confirmationCode }}</h1>
    <div>
      <img src="" alt="res photo">
    </div>
    <p>reservation description</p>
  </section>
  <!-- <p> {{ $route.params.confirmationCode }} </p> -->
</template>

<style scoped>
.single-reservation {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
</style>
