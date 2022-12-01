<template>
  <div>
    <game-detail
      :game-id="gameQuery.id"
      :game-title="gameQuery.title"
      :game-thumbnail="gameQuery.thumbnail"
      :game-description="gameQuery.short_description"
    />
  </div>
</template>

<script>
import GameDetail from '~/components/detail/GameDetail.vue'
export default {
  components: {
    GameDetail,
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
