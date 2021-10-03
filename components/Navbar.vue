<template>
  <div class="mb-2 shadow-lg navbar bg-neutral text-neutral-content">
    <div class="flex-1 px-2 mx-2">
      <span class="text-lg font-bold"> Nuxt-Learning </span>
    </div>
    <div
      class="absolute right-0 flex-none mx-0 overflow-hidden duration-300 top-16 md:top-2 bg-neutral md:mx-2 md:flex"
      :class="open ? 'max-h-full p-2' : 'max-h-0 p-0 md:max-h-full md:p-2'"
    >
      <div class="flex flex-col items-stretch md:flex-row">
        <nuxt-link to="/">
          <a class="btn btn-ghost btn-sm rounded-btn"> Home </a>
        </nuxt-link>
        <nuxt-link to="/about">
          <a class="btn btn-ghost btn-sm rounded-btn"> About </a>
        </nuxt-link>
      </div>
    </div>
    <div class="inline md:hidden">
      <button class="btn btn-square btn-ghost" @click="open = !open">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          class="inline-block w-6 h-6 stroke-current"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          ></path>
        </svg>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      open: false,
    }
  },
}
</script>
