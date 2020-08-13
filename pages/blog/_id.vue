<template>
  <div>
    <h1>{{ post.title }}</h1>
    <p>{{ post.description }}</p>
    <button @click="nextPost">Next Post</button>
  </div>
</template>

<script>
export default {
  loading: false,
  data() {
    return {
      currentPostId: 1,
    }
  },
  async asyncData({ params, $http }) {
    const post = await $http.$get(`https://api.nuxtjs.dev/posts/${params.id}`)
    // console.log('Data -> post', post)
    return { post }
  },

  head() {
    return {
      title: this.post.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.post.description,
        },
      ],
    }
  },

  methods: {
    nextPost() {
      this.currentPostId++
      //   this.$route.params.id = this.currentPostId
      //   console.log('nextPost -> this.$route.params.id', this.$route.params.id)
      this.$router.push({
        name: 'blog-id',
        params: {
          id: this.currentPostId,
        },
      })
    },
  },
}
</script>
