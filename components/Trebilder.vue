<template>
  <div>
    <div class="flex flex-col items-center lg:flex-row lg:justify-center">
      <nuxt-link
        to="/storahundar"
        class="
          transform
          transition
          duration-500
          ease-in-out
          hover:scale-105
          w-full
          2xl:mr-8
          lg:ml-20
        "
      >
        <img
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQr4cWaLq3J2dy0b18PiwvVKdcHQAO5rDEz7g&usqp=CAU"
          alt="en hund"
          class="my-10 mx-2 w-full 2xl:w-full lg:w-80 lg:h-80 h-96 object-cover"
        />
        <div class="flex justify-center">Stora hundar</div>
      </nuxt-link>
      <nuxt-link
        to="/raser"
        class="
          transform
          transition
          duration-500
          ease-in-out
          hover:scale-105
          w-full
          2xl:mr-8
        "
      >
        <img
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQBbpPTIIdU63umUOqRddN5YSqSn_fGx0w6ZQ&usqp=CAU"
          alt="en hund"
          class="my-10 mx-2 w-full lg:w-80 2xl:w-full lg:h-80 h-96 object-cover"
        />
        <div class="flex justify-center">Raser</div>
      </nuxt-link>
      <nuxt-link
        to="/smahundar"
        class="
          transform
          transition
          duration-500
          ease-in-out
          hover:scale-105
          w-full
          lg:mr-20
        "
      >
        <img
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRqVMxrj6c6H3V4S466shwl_bVp1JjQqm-KhQ&usqp=CAU"
          alt="en hund"
          class="my-10 mx-2 w-full lg:h-80 h-96 object-cover"
        />
        <div class="flex justify-center">Små hundar</div>
      </nuxt-link>
    </div>
    <div class="flex justify-center justify-evenly"></div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
</style>