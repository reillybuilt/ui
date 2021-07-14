<template>
  <nav class="bg-white shadow">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="h-24 flex items-center justify-between">
        <!-- logo -->
        <div class="flex-shrink-0 w-32 h-9 bg-gray-200"></div>
        <!-- mobile menu button -->
        <div class="sm:hidden">
          <button
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
            aria-expanded="false"
            @click="show = !show"
          >
            <span class="sr-only">Open main menu</span>
            <svg
              class="h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                :d="show ? 'M6 18L18 6M6 6l12 12' : 'M4 6h16M4 12h16M4 18h16'"
              />
            </svg>
          </button>
        </div>
        <!-- navbar links -->
        <div class="hidden sm:flex sm:items-center sm:space-x-8">
          <nuxt-link
            v-for="({ to, text }, i) in links"
            :key="`navbar-${i}`"
            :to="to"
            class="text-gray-900 text-sm font-medium"
          >
            {{ text }}
          </nuxt-link>
        </div>
      </div>
    </div>
    <!-- mobile modal -->
    <transition
      enter-active-class="duration-150 ease-out"
      enter-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="duration-100 ease-in"
      leave-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-95"
    >
      <div
        v-show="show"
        class="absolute top-0 inset-0 p-2 transition transform origin-top-right md:hidden bg-gray-900 bg-opacity-25"
      >
        <div
          v-click-outside="hide"
          class="rounded-lg shadow-md bg-white ring-1 ring-black ring-opacity-5 overflow-hidden"
        >
          <div class="px-5 pt-4 flex items-center justify-between">
            <div>
              <!-- replace w/ logo -->
              <div class="w-16 h-9 bg-gray-200"></div>
            </div>
            <div class="-mr-2">
              <button
                type="button"
                class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
                @click="show = false"
              >
                <span class="sr-only">Close menu</span>
                <svg
                  class="h-6 w-6"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M6 18L18 6M6 6l12 12"
                  />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      links: [
        {
          text: 'Link',
          to: '/',
        },
      ],
    }
  },
  watch: {
    $route() {
      this.hide()
    },
  },
  methods: {
    hide() {
      this.show = false
    },
  },
  head() {
    return {
      bodyAttrs: {
        class: this.show ? 'overflow-hidden' : null,
      },
    }
  },
}
</script>
