<template>
  <div class="flex flex-wrap">
    <img
      src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQBdfU_2PIICuo4UKYM3XiDJyMopIR5kWSY2w&usqp=CAU"
      alt="en hund"
      class="w-full pt-20"
    />
    <div class="w-full">
      <MittenComponent />
    </div>
    <div class="w-full mt-32 lg:mt-52">
      <Trebilder />
      <div>
        <div class="lg:w-4/6 lg:mx-auto flex justify-center mt-28 lg:mt-52">
          <h1 class="text-lg">Recent</h1>
        </div>
        <div
          class="
            flex flex-col
            items-center
            lg:flex-row lg:justify-center
            mx-10
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
    </div>
  </div>
</template>

<script>
import MittenComponent from '../components/MittenComponent.vue'
export default {
  components: { MittenComponent },
  name: 'IndexPage',
  async asyncData ({ $content }) {
    let posts = await $content('posts').sortBy('id', 'desc').limit(3).without(['body']).fetch()

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

<style>
</style>
