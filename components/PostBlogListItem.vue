<template>
  <div
    class="
      flex
      lg:flex-row
      flex-col
      w-full
      lg:w-120 lg:h-80
      h-auto
      transform
      transition
      duration-500
      ease-in-out
      hover:scale-105
      border-2
      mx-auto
      my-5
      lg:my-6 lg:mx-auto
      shadow-md
    "
  >
    <img
      :src="item1.image"
      alt="post image"
      class="h-full w-full lg:w-1/3 object-cover"
    />
    <div>
      <h3 class="text-xl p-4">{{ item1.title }}</h3>
      <p class="p-4 mb-6 lg:m-0">{{ item1.description }}</p>
      <p class="p-4 absolute right-0 bottom-0">{{ item1.date }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['item1'],
  data () {
    return {

    }
  }
}
</script>