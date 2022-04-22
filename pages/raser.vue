<template>
  <div class="flex flex-col pt-20 h-full">
    <div class="w-full flex justify-center">
      <h1 class="text-3xl border-b-2 border-green-500 mt-10">5 olika raser</h1>
    </div>
    <div>
      <Labrador></Labrador>
    </div>
    <div>
      <Schafer></Schafer>
    </div>
    <div>
      <NewFoundland></NewFoundland>
    </div>
    <div>
      <GoldenRetriver></GoldenRetriver>
    </div>
    <div>
      <Malteser></Malteser>
    </div>
  </div>
</template>

<script>
import Labrador from '../components/Labrador.vue'
export default {
  components: { Labrador },
  data () {

  }
}
</script>

<style>
</style>