<template>
  <div class="flex flex-col place-items-center pt-20">
    <div
      class="
        bg-local bg-cover
        w-full
        flex
        justify-center
        p-80
        text-white text-8xl
        font-serif
      "
      style="
        background-image: url(https://k9ti.org/wp-content/uploads/2019/02/puppy-3688871_1920-1.jpg);
      "
    >
      Photos
    </div>
    <p v-if="$fetchState.pending">Fetching photos...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else class="mt-10 w-full flex flex-wrap justify-center">
      <div class="flex flex-wrap w-full justify-center">
        <img
          :src="ras.message[0]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[1]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[2]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[3]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[4]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[5]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[6]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[7]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
        <img
          :src="ras.message[8]"
          class="object-cover w-1/4 h-64 m-3 shadow-xl"
        />
      </div>
      <button
        @click="$fetch"
        class="
          border-2
          mb-5
          mt-2
          p-2
          rounded-xl
          border-black
          shadow-xl
          bg-hast-800
          hover:bg-hast-300
        "
      >
        Click to get some new photos
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ras: []
    }
  },
  async fetch () {
    this.ras = await fetch(
      'https://dog.ceo/api/breeds/image/random/9'
    ).then(res => res.json())
  }
}
</script>

<style>
</style>