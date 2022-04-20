<template>
  <div
    class="
      transform
      transition
      duration-500
      ease-in-out
      hover:scale-105
      border-2
      shadow-md
      lg:w-64
      w-full
      h-96
      lg:h-auto
    "
  >
    <img
      :src="item.image"
      alt="blogg image"
      class="h-2/3 lg:h-80 w-full lg:w-64 object-cover"
    />
    <div class="flex-col justify-center h-52">
      <h3 class="w-full lg:w-64 text-xl">{{ item.title }}</h3>
      <p class="w-full lg:w-64">{{ item.description }}</p>
      <p class="p-4 absolute right-0 bottom-0">{{ item.date }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['item'],
  data () {
    return {

    }
  }
}
</script>