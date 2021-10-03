<template>
  <div>
    <Navbar />

    <div class="max-w-xl md:mx-auto mx-5 mt-10">
      <div v-if="$nuxt.isOffline">You are offline :(</div>
      <div v-if="$nuxt.isOnline">
        <Nuxt />
      </div>
    </div>
  </div>
</template>
