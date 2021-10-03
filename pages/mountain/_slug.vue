<template>
  <div class="pb-10">
    <div class="alert alert-info">Fetching data using asyncData hook</div>
    <h2 class="my-2 text-3xl font-semibold">
      {{ mountain.title }}
    </h2>
    <div class="flex gap-2 my-2">
      <div v-for="country in mountain.countries" :key="country">
        <div class="p-2 font-semibold bg-gray-200 rounded-xl">
          {{ country }}
        </div>
      </div>
    </div>
    <img :src="mountain.image" class="object-cover w-full my-5 rounded-lg" />

    <p class="mb-2 text-xl font-semibold">height: {{ mountain.height }}</p>
    <p>{{ mountain.description }}</p>
    <button class="mt-5 btn btn-sm btn-ghost" @click="$router.go(-1)">
      Back
    </button>
  </div>
</template>

<script>
export default {
  async asyncData({ params, $axios }) {
    const mountain = await $axios.$get(
      'https://api.nuxtjs.dev/mountains/' + params.slug
    )
    return { mountain }
  },
}
</script>

<style scoped>
img {
  max-height: 700px;
}
</style>
