<template>
  <div class="flex flex-col place-items-center pt-20">
    <div
      class="
        bg-local bg-cover
        w-full
        flex
        justify-center
        lg:p-80
        p-32
        text-white text-6xl
        lg:text-8xl
        font-serif
      "
      style="
        background-image: url(https://studier.se/wp-content/uploads/2019/01/Jobba-med-hundar.jpg);
      "
    >
      Blogg
    </div>
    <h17 class="text-lg mt-4">All posts</h17>

    <div
      @click="goToPost(post.id)"
      class="w-2/3"
      v-for="post in posts"
      :key="post.id"
    >
      <PostBlogListItem :item1="post"></PostBlogListItem>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  async asyncData ({ $content }) {
    let posts = await $content('posts').sortBy('id', 'desc').without(['body']).fetch()

    return {
      posts
    }
  },
  methods: {
    goToPost (id) {
      this.$router.push('/postDetails/' + id)
    }
  }
}
</script>