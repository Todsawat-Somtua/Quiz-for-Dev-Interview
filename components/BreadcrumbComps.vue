<template>
  <div class="py-3 max-md:ml-7">
    <label class="font-bold">
      <NuxtLink to="/"> List </NuxtLink>
      / {{ gameTitle }}
    </label>
  </div>
</template>

<script>
export default {
  props: {
    gameTitle: {
      type: String,
      required: true,
    },
  },
}
</script>
