<template>
  <div class="w-full flex flex-col md:flex-row">
    <img
      src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRD-e353SZtDxWr8lnecu27jk-XyeDAoLj0fw&usqp=CAU"
      alt="en hund"
      class="mx-10 lg:w-1/3 lg:mt-16 lg:ml-16 order-last lg:order-first"
    />
    <div class="m-8 w-full p-10 lg:w-2/4 lg:pt-8 lg:ml-1">
      <h2 class="text-2xl">Snobben är välkommen</h2>
      <p class="text-m mt-8">
        Hejsan här kan du trycka ifall du vill spränga jorden. <br />
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Tempor nec feugiat
        nisl pretium fusce id. Pellentesque dignissim enim sit amet venenatis
        urna. Rutrum quisque non tellus orci ac auctor augue mauris. Id aliquet
        lectus proin nibh. Odio morbi quis commodo odio aenean sed. Eget gravida
        cum sociis natoque penatibus et magnis.
      </p>
      <div
        class="
          bg-hast-800
          hover:bg-hast-500
          w-20
          h-8
          flex
          justify-center
          rounded-xl
          shadow-xl
          lg:mt-16
          mt-6
        "
      >
        <nuxt-link to="/blogg">Pang!</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
</style>