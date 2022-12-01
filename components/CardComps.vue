<template>
  <div>
    <NuxtLink
      :to="`/detail/${gameId}`"
      class="flex flex-col mx-auto bg-[#FFFFFF] rounded-lg max-md:flex-row hover:bg-gray-300 max-md:h-[100px] md:w-[320px] md:h-[340px] md:p-3"
    >
      <img
        id="image"
        :src="gameThumbnail"
        :alt="gameTitle"
        class="max-md:rounded-lg lg:mb-6 max-md:w-[136px]"
      />
      <div class="flex flex-col px-2 justify-center leading-normal">
        <label for="image" class="font-bold text-[#273253]">{{
          gameTitle
        }}</label>
        <p class="lg:mt-2 font-normal text-[#838383] text-xs">
          {{ gameDescription }}
        </p>
      </div>
    </NuxtLink>
  </div>
</template>

<script>
export default {
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
