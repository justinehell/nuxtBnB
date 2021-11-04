<template>
  <div>
    <img :src="home.images[0]" style="width: 200px" />
    <p>{{ home.title }}</p>
    <p>{{ home.location.adress }} {{ home.location.city }}</p>
    <p>{{ home.location.state }} {{ home.guests }} guests</p>
    <p>{{ home.pricePerNight }} / night</p>
  </div>
</template>
<script>
export default {
  name: 'HomeCard',
  props: {
    home: {
      type: Object,
      required: true,
    },
  },
}
</script>
