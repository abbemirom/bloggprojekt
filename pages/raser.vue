<template>
  <div class="flex place-content-center">
    <p v-if="$fetchState.pending">Fetching mountains...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <h1>Nuxt Mountains</h1>
      <ul>
        <li v-for="ras of ras" :key="ras"></li>
      </ul>
      <button @click="$fetch">Refresh</button>
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
      'https://dog.ceo/api/breeds/list/all'
    ).then(res => res.json())
  }
}

</script>

<style>
</style>