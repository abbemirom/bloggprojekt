<template>
  <div class="pt-8 lg:pt-20">
    <div
      class="
        lg:w-4/6 lg:mx-auto lg:border-2
        px-20
        pb-10
        mt-10
        lg:shadow-lg lg:rounded-md
      "
    >
      <h1 class="text-5xl mb-8 pt-24">{{ post.title }}</h1>
      <p class="mb-8">{{ post.description }}</p>
      <img :src="post.image" class="w-full mb-4" />
      <nuxt-content :document="post"></nuxt-content>
      <div class="border-t-2 my-10 border-t-gray-500 h-10 flex">
        <a
          class="flex self-center mx-3 mt-7"
          href="https://www.instagram.com/explore/tags/puppies/"
        >
          <img
            src="https://marjanvanaubel.com/wp-content/uploads/2019/11/instagram-logo.png"
            class="w-10"
          />
        </a>
        <a
          href="https://www.facebook.com/hashtag/dog"
          class="flex self-center mx-3 mt-7"
        >
          <img
            src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Facebook_Logo_%282019%29.png/1024px-Facebook_Logo_%282019%29.png"
            class="w-10 filter grayscale"
          />
        </a>
      </div>
      <div class="border-t-2 mb-10 border-t-gray-500 flex"></div>
    </div>
    <div class="w-4/6 mx-auto mt-10 flex justify-between">
      <div class="m-3">Recent</div>
      <nuxt-link to="/blogg" class="m-3">See all</nuxt-link>
    </div>
    <div
      class="
        flex flex-col
        items-center
        lg:flex-row lg:justify-center
        mx-20
        lg:mx-10
        mb-10
      "
    >
      <div
        @click="goToPost(post.id)"
        class="w-full lg:w-64 m-4"
        v-for="post in posts"
        :key="post.id"
      >
        <PostListItem :item="post"></PostListItem>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  async asyncData ({ $content, params }) {

    let post = await $content('posts/post' + params.id).fetch()
    let posts = await $content('posts').sortBy('id', 'desc').limit(3).without(['body']).fetch()
    console.log(post)

    return {
      post,
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