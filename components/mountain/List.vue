<template>
  <div>
    <div class="flex justify-between">
      <h3 class="text-3xl font-semibold">Mountain</h3>
      <button class="btn btn-ghost" @click="$fetch">Refresh</button>
    </div>
    <p class="text-gray-500">Fetching data using fetch hook</p>
    <p v-if="$fetchState.pending">Loading...</p>
    <p v-else-if="$fetchState.error">Something went wrong :(</p>
    <div v-else class="grid grid-cols-1 gap-10 mt-5 md:grid-cols-2">
      <div v-for="mountain in mountains" :key="mountain.slug">
        <MountainCard :mountain="mountain" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    mountains: [],
  }),
  async fetch() {
    this.mountains = await this.$axios.$get(`https://api.nuxtjs.dev/mountains`)
  },
}
</script>
