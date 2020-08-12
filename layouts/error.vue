<template>
  <div class="container">
    <h1 class="text-xl text-red-500" v-if="error.statusCode === 404">
      Page not found
    </h1>
    <h1 v-else>An error occurred</h1>
    <div class="mx-4">
      <NuxtLink to="/" class="text-blue-500">Home page</NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'error',
}
</script>
