<template>
  <div>
    <nuxt-link to="/">Home</nuxt-link>
    <div class="flex">
      <img
        v-for="image in home.images"
        :key="image"
        alt="something descriptive..."
        :src="image"
        width="200"
        height="150"
      />
    </div>
    <p>{{ home.title }}</p>
    <p>${{ home.pricePerNight }} / night</p>

    <p>
      <span
        ><img
          src="/images/marker.svg"
          width="20"
          height="20"
          class="inline-block"
      /></span>
      {{ home.location.adress }} {{ home.location.city }}
      {{ home.location.state }}
      {{ home.location.country }}
    </p>
    <p>
      <span
        ><img
          src="/images/star.svg"
          width="20"
          height="20"
          class="inline-block" /></span
      >{{ home.reviewValue }}
    </p>
    <p>
      {{ home.guests }} guests, {{ home.bedrooms }} rooms,
      {{ home.guests }} beds, {{ home.guests }} bath
    </p>
  </div>
</template>

<script>
import homes from '~/data/homes'
export default {
  data() {
    return {
      home: {},
    }
  },
  head() {
    return {
      title: this.home.title,
    }
  },
  created() {
    const home = homes.find((home) => home.objectID === this.$route.params.id)
    this.home = home
  },
}
</script>
