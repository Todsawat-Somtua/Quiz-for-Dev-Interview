<template>
  <div
    class="grid grid-cols-2 mt-[2.5%] w-fit max-md:p-2 md:mx-auto gap-4 lg:grid-cols-3 max-md:grid-cols-1"
  >
    <card-comps
      v-for="game in games"
      :key="game.id"
      :game-id="game.id"
      :game-title="game.title"
      :game-thumbnail="game.thumbnail"
      :game-description="game.short_description"
    />
  </div>
</template>

<script>
import CardComps from '~/components/CardComps.vue'

export default {
  components: {
    CardComps,
  },
  layout: 'header',
  async asyncData({ $axios }) {
    const games = await $axios.$get('/games')
    return { games }
  },
}
</script>

<style>
body {
  background-color: #f5f5f5;
}
</style>
