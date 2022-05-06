<template>
    <header class="top-0 left-0 z-40 fixed bg-white w-full border-b border-gray-200">
      <nav class="container mx-auto flex flex-wrap justify-between items-center">
        <router-link to="/" @click="scrollToTop"><div class="font-bold text-xl text-gray-500">Kirix Strata</div></router-link>
        <div class="block lg:hidden"> <!-- hamburger -->
          <button @click="toggleBurger" class="flex items-center px-3 py-2 border rounded border-gray-500 hover:text-gray-700 hover:border-gray-700">
            <svg class="current-color h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" fill="gray" /></svg>
          </button>
        </div>
        <ul class="nav-btn-container uppercase tracking-wide font-bold text-sm pb-4 w-full block flex-grow lg:flex lg:flex-initial lg:w-auto lg:pb-0 items-center"
            :class="isOpen ? 'block': 'hidden'"
        >
          <li><router-link to="/" @click="scrollToTop"><div class="nav-btn py-6 lg:px-4">Home</div></router-link></li>
          <li><router-link to="/" @click="scrollToTop"><div class="nav-btn py-6 lg:px-4">Explore</div></router-link></li>
          <li><router-link to="/" @click="scrollToTop"><div class="nav-btn py-6 lg:px-4">Documentation</div></router-link></li>
          <li><router-link to="/" @click="scrollToTop"><div class="nav-btn py-6 lg:px-4">GitHub</div></router-link></li>
        </ul>
      </nav>
    </header>
</template>

<script>
  export default {
    name: 'AppHeader',

    data() {
      return {
        isOpen: false,
      }
    },
    methods: {
      scrollToTop() {
        this.isOpen = false
        window.scrollTo(0,0);
      },
      toggleBurger() {
        this.isOpen = !this.isOpen
      }
    }
  }
</script>


<style scoped>
  .nav-btn {
    color: theme('colors.gray.500');
  }
  .nav-btn:hover {
    background-color: theme('colors.gray.100');
  }
</style>
