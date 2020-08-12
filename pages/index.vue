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
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
</style>
