<template>
  <div class="flex">
    <div v-for="home in homes" :key="home.objectID" class="m-4">
      <home-card :home="home" />
    </div>
  </div>
</template>

<script>
import homes from '~/data/homes'
export default {
  data() {
    return {
      homes: homes.slice(0, 3),
    }
  },
  head() {
    return {
      title: 'Homepage',
      meta: [
        {
          name: 'descripton',
          content: 'This is a homepage!',
          hid: 'description',
        },
      ],
    }
  },
}
</script>
