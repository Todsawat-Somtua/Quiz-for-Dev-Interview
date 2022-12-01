<template>
  <div>
    <game-card
      :game-id="gameQuery.id"
      :game-title="gameQuery.title"
      :game-thumbnail="gameQuery.thumbnail"
      :game-description="gameQuery.short_description"
    />
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
