<template>
  <div class="md:w-[60%] md:h-[40%] mx-auto">
    <breadcrumb-comps :game-title="gameTitle" />
    <div class="md:bg-[#FFFFFF] p-7">
      <img
        id="image"
        :src="gameThumbnail"
        :alt="gameTitle"
        class="w-full shadow-2xl rounded-lg"
      />
      <div
        class="my-3 max-md:bg-[#FFFFFF] max-md:rounded-lg max-md:px-6 max-md:py-4"
      >
        <label class="font-bold text-base">{{ gameTitle }}</label>
        <p class="mt-5">{{ gameDescription }}</p>
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
    gameId: {
      type: Number,
      required: true,
    },
    gameTitle: {
      type: String,
      required: true,
    },
    gameThumbnail: {
      type: String,
      required: true,
    },
    gameDescription: {
      type: String,
      required: true,
    },
  },
}
</script>
