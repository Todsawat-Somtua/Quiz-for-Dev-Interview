<template>
  <div>
    <game-card :current-game="gameQuery" />
  </div>
</template>

<script>
import GameCard from '~/components/detail/GameCard.vue'
export default {
  components: {
    GameCard,
  },
  layout: 'header',
  validate(data) {
    return /^\d+$/.test(data.params.id)
  },
  async asyncData({ params, $axios }) {
    const gameQuery = await $axios.$get('/game', { params })
    return { gameQuery }
  },
}
</script>
