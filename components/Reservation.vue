<template>
  <nuxt-link :to="'/reservations/' + confirmationCode">
    <article class="reservation">
      <div class="thumbnail" :style="{ backgroundImage:'url(' + cityImage + ')'}" />
      <h2>{{ city }}</h2>
      <p>{{ preview }}</p>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  // changed json mock instead
  /* filters: {
    removeImgUrlBrackets: (value) => {
      if (!value) { return '' }
      value = value.replace('<', '').replace('>', '')
      return value
    }
  }, */
  props: {
    cityImage: {
      type: String,
      default: ''
    },
    city: {
      type: String,
      default: ''
    },
    confirmationCode: {
      type: String,
      default: 'XXXXXX'
    },
    preview: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
a {
  color: black;
  text-decoration: none;
}
.reservation {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
  margin: 10px;
}
.thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>
