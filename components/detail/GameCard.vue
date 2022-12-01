<template>
  <div class="md:w-[60%] md:h-[40%] mx-auto">
    <breadcrumb-comps :game-title="currentGame.title" />
    <div class="md:bg-[#FFFFFF] p-7">
      <img
        id="image"
        :src="currentGame.thumbnail"
        :alt="currentGame.title"
        class="w-full shadow-2xl rounded-lg"
      />
      <div
        class="my-3 max-md:bg-[#FFFFFF] max-md:rounded-lg max-md:px-6 max-md:py-4"
      >
        <label class="font-bold text-base">{{ currentGame.title }}</label>
        <p class="mt-5">{{ currentGame.short_description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import BreadcrumbComps from '../BreadcrumbComps.vue'
export default {
  components: {
    BreadcrumbComps,
  },
  layout: 'header',
  props: {
    currentGame: {
      type: Object,
      required: true,
    },
  },
}
</script>
