<template>
  <div class="m-4">
    <h1 class="text-xl text-red-500" v-if="error.statusCode === 404">
      Page not found
    </h1>
    <h1 v-else>An error occurred</h1>
    <div v-if="$nuxt.isOffline">You are offline</div>
    <div v-else>You are online</div>
    <div>
      <NuxtLink to="/" class="text-blue-500">Home page</NuxtLink>
    </div>
    <div>
      <button @click="refresh" class="my-3 p-2 bg-teal-500 text-teal-100">
        Refresh
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'error',

  methods: {
    refresh() {
      console.log('refreshing...')
      this.$nuxt.refresh()
    },
  },
}
</script>
