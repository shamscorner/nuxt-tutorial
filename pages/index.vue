<template>
  <div class="container">
    <div>
      <Logo class="p-4" />
      <h1 class="text-lg">
        TutorialApp
      </h1>
      <div class="my-2">
        <NuxtLink to="/about" class="button--grey">About Us</NuxtLink>
      </div>
      <div>
        <h1>I am rendered on the {{ renderedOn }} side</h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    window.onNuxtReady(() => {
      console.log('Nuxt.js is ready and mounted')
    })
  },

  asyncData() {
    return {
      renderedOn: process.client ? 'client' : 'server',
    }
  },
}
</script>

<style>
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
</style>
