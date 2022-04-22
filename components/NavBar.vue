<template>
  <nav class="fixed w-full p-6 bg-green-900">
    <div class="flex items-center justify-between">
      <!-- Header logo -->
      <div>
        <Tailwind />
      </div>

      <!-- Mobile toggle -->
      <div class="md:hidden">
        <button @click="drawer">
          <svg
            class="h-8 w-8 fill-current text-white"
            fill="none"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>

      <!-- Navbar -->
      <div class="hidden md:block">
        <ul class="flex justify-center space-x-8 text-sm font-sans text-white">
          <li>
            <nuxt-link to="/" class="active">Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/blogg">Blog</nuxt-link>
          </li>
          <li><nuxt-link to="/photos">Photos</nuxt-link></li>
          <li><nuxt-link to="/About">About</nuxt-link></li>
        </ul>
      </div>

      <!-- Dark Background Transition -->
      <transition
        enter-class="opacity-0"
        enter-active-class="ease-out transition-medium"
        enter-to-class="opacity-100"
        leave-class="opacity-100"
        leave-active-class="ease-out transition-medium"
        leave-to-class="opacity-0"
      >
        <div
          @keydown.esc="isOpen = false"
          v-show="isOpen"
          class="z-10 fixed inset-0 transition-opacity"
        >
          <div
            @click="isOpen = false"
            class="absolute inset-0 bg-black opacity-50"
            tabindex="0"
          ></div>
        </div>
      </transition>

      <!-- Drawer Menu -->
      <aside
        class="
          p-5
          transform
          top-0
          left-0
          w-64
          bg-green
          fixed
          h-full
          overflow-auto
          ease-in-out
          transition-all
          duration-300
          z-30
        "
        :class="isOpen ? 'translate-x-0' : '-translate-x-full'"
      >
        <div class="close">
          <button
            class="absolute top-0 right-0 mt-4 mr-4"
            @click="isOpen = false"
          >
            <svg
              class="w-6 h-6"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>

        <span @click="isOpen = false" class="flex w-full items-center border-b">
          <Tailwind />
        </span>

        <ul class="divide-y font-sans">
          <li>
            <nuxt-link to="/" class="my-4 inline-block">Home</nuxt-link>
          </li>

          <li>
            <nuxt-link to="/blogg" class="my-4 inline-block"> blogg </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/photos" class="my-4 inline-block">Photos</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/about" class="my-4 inline-block"> about </nuxt-link>
          </li>
        </ul>

        <div class="follow">
          <p class="italic font-sans text-sm"></p>
          <div class="social flex space-x-5 mt-4">
            <a href="https://www.facebook.com/hashtag/dog">
              <svg
                aria-hidden="true"
                focusable="false"
                data-prefix="fab"
                data-icon="facebook-f"
                class="h-5 w-5 fill-current text-gray-600"
                role="img"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 320 512"
              >
                <path
                  fill="currentColor"
                  d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
                ></path>
              </svg>
            </a>
            <a href="https://www.instagram.com/explore/tags/puppies/">
              <svg
                aria-hidden="true"
                focusable="false"
                data-prefix="fab"
                data-icon="instagram"
                class="h-5 w-5 fill-current text-gray-600"
                role="img"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 448 512"
              >
                <path
                  fill="currentColor"
                  d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
                ></path>
              </svg>
            </a>
          </div>
        </div>
      </aside>
    </div>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      isOpen: false
    }
  },
  methods: {
    drawer () {
      this.isOpen = !this.isOpen
    }
  },
  watch: {
    isOpen: {
      immediate: true,
      handler (isOpen) {
        if (process.client) {
          if (isOpen) document.body.style.setProperty("overflow", "hidden")
          else document.body.style.removeProperty("overflow")
        }
      }
    }
  },
  mounted () {
    document.addEventListener("keydown", e => {
      if (e.keyCode == 27 && this.isOpen) this.isOpen = false
    })
  }
};
</script>

<style>
.nuxt-link-exact-active {
  border-bottom: 2px solid rgb(182, 213, 241);
  padding-bottom: 5px;
}
</style>
