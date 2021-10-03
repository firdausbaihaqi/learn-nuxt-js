<template>
  <div class="card bordered shadow-md">
    <figure>
      <img class="h-40 object-cover" :src="mountain.image" />
    </figure>
    <div class="card-body">
      <h2 class="card-title">
        {{ mountain.title }}
      </h2>
      <div>
        <p class="line-clamp-3">{{ mountain.description }}</p>
      </div>
      <div class="card-actions justify-end">
        <nuxt-link :to="'/mountain/' + mountain.slug">
          <button class="btn btn-sm btn-ghost">Read More</button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    mountain: {
      type: Object,
      default: null,
    },
  },
}
</script>
