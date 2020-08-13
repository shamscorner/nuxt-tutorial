<template>
  <div>
    <h1 class="text-lg">Welcome to the blog post</h1>

    <ul>
      <li v-for="post in posts" :key="post.id">
        <h3 class="text-lg text-blue-600 mt-4">{{ post.title }}</h3>
        <p>{{ post.description }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  layout: 'blog',

  head: {
    title: 'Welcome to Blog',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'This is a blog home page',
      },
    ],
  },

  data() {
    return {
      posts: [],
    }
  },

  async fetch() {
    this.posts = await fetch('https://api.nuxtjs.dev/posts').then((res) =>
      res.json()
    )
  },

  fetchOnServer: false, // this will fetch the posts first and then will load the page -> client side
}
</script>

<style lang="scss" scoped></style>
