<template>
  <nav class="flex relative h-auto md:fixed w-full items-center justify-end md:justify-between flex-wrap bg-steel-500 p-4">
    <button class="hidden sm:fixed sm:block inset-0 w-full h-screen focus:outline-none bg-black opacity-0 bgBox"
      @click="isOpen = !isOpen"
      v-if="isOpen"
      tabindex="-1"
    >
    </button>
    <div class="flex w-full justify-between lg:hidden">
      <a href="#responsive-header" class="flex w-3/5 font-display font-semibold bg-coral-500 justify-center text-center text-white hover:text-sand-500 mr-0 p-2 rounded">
        Nick Moore
      </a>
      <button class="flex items-center px-3 py-2 right-0 border rounded text-white border-white hover:text-white hover:border-white" @click="isOpen = !isOpen">
        <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
      </button>
    </div>
    <div class="hidden lg:block w-full flex-grow lg:flex lg:items-center lg:w-auto">
      <div class="justify-center text-lg lg:flex-grow">
        <a href="#responsive-header" class="block lg:inline-block lg:mt-0 font-display font-semibold bg-coral-500 text-white text-center md:text-left hover:text-sand-500 mr-0 md:mr-4 p-2 rounded">
          Nick Moore
        </a>
        <a href="#projects" class="block lg:inline-block mt-2 md:mt-0 font-body font-light text-right md:text-center text-white hover:text-sand-500 mr-4">
          Projects
        </a>
        <a href="#responsive-header" class="block lg:inline-block mt-2 md:mt-0 font-body font-light text-right md:text-center text-white hover:text-sand-500 mr-4">
          Resume
        </a>
        <a href="#responsive-header" class="block lg:inline-block mt-2 md:mt-0 font-body font-light text-right md:text-center text-white hover:text-sand-500 mr-4">
          Contact
        </a>
      </div>
      <div class="flex justify-center md:justify-end w-full md:w-1/3">
        <a href="https://github.com/nmoore14" class="inline-block text-sm p2 leading-none bg-steel-300 rounded text-white hover:text-teal-500 hover:bg-coral-500 mx-2 mt-4 lg:mt-0">
          <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-github" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z"/>
            <path d="M9 19c-4.286 1.35-4.286-2.55-6-3m12 5v-3.5c0-1 .099-1.405-.5-2 2.791-.3 5.5-1.366 5.5-6.04a4.567 4.567 0 0 0 -1.333 -3.21a4.192 4.192 0 0 0 -.08 -3.227s-1.05-.3-3.476 1.267a12.334 12.334 0 0 0 -6.222 0C6.462 2.723 5.413 3.023 5.413 3.023a4.192 4.192 0 0 0 -.08 3.227A4.566 4.566 0 0 0 4 9.486c0 4.64 2.709 5.68 5.5 6.014-.591.589-.56 1.183-.5 2V21" />
          </svg>
        </a>
        <a href="https://www.linkedin.com/in/nick-moore-2258663b/" class="inline-block text-sm p2 leading-none bg-steel-300 rounded text-white hover:text-teal-500 hover:bg-coral-500 mt-4 lg:mt-0">
          <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-linkedin" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z"/>
            <rect x="4" y="4" width="16" height="16" rx="2" />
            <line x1="8" y1="11" x2="8" y2="16" />
            <line x1="8" y1="8" x2="8" y2="8.01" />
            <path d="M12 16v-5" />
            <path d="M16 16v-3a2 2 0 0 0 -4 0" />
          </svg>
        </a>
        <a href="https://codepen.io/nmoore1407/#" class="inline-block text-sm p2 leading-none bg-steel-300 rounded text-white hover:text-teal-500 hover:bg-coral-500 mx-2 mt-4 lg:mt-0">
          <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-codepen" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z"/>
            <path d="M3 15l9 6l9 -6l-9 -6l-9 6" />
            <path d="M3 9l9 6l9 -6l-9 -6l-9 6" />
            <line x1="3" y1="9" x2="3" y2="15" />
            <line x1="21" y1="9" x2="21" y2="15" />
            <line x1="12" y1="3" x2="12" y2="9" />
            <line x1="12" y1="15" x2="12" y2="21" />
          </svg>
        </a>
      </div>
    </div>
    <div :class="isOpen ? 'block' : 'hidden'" class="w-full flex-grow lg:hidden lg:items-center lg:w-auto">
      <div class="mt-4 justify-center text-lg lg:flex-grow">
        <a href="#projects" class="block mt-2 md:mt-2 w-1/2 bg-steel-300 p-2 float-right font-body text-2xl font-light text-right text-white hover:text-sand-500 mr-4 rounded">
          Projects
        </a>
        <a href="#responsive-header" class="block mt-2 md:mt-2 w-2/3 bg-steel-300 p-2 float-right font-body text-2xl font-light text-right text-white hover:text-sand-500 mr-4 rounded">
          Resume
        </a>
        <a href="#responsive-header" class="block mt-2 md:mt-2 w-5/6 bg-steel-300 p-2 float-right font-body text-2xl font-light text-right text-white hover:text-sand-500 mr-4 rounded">
          Contact
        </a>
      </div>
      <div class="flex justify-center w-full">
        <a href="https://github.com/nmoore14" class="inline-block text-sm p2 leading-none bg-steel-300 rounded text-white hover:text-teal-500 hover:bg-coral-500 mx-2 mt-4 lg:mt-0">
          <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-github" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z"/>
            <path d="M9 19c-4.286 1.35-4.286-2.55-6-3m12 5v-3.5c0-1 .099-1.405-.5-2 2.791-.3 5.5-1.366 5.5-6.04a4.567 4.567 0 0 0 -1.333 -3.21a4.192 4.192 0 0 0 -.08 -3.227s-1.05-.3-3.476 1.267a12.334 12.334 0 0 0 -6.222 0C6.462 2.723 5.413 3.023 5.413 3.023a4.192 4.192 0 0 0 -.08 3.227A4.566 4.566 0 0 0 4 9.486c0 4.64 2.709 5.68 5.5 6.014-.591.589-.56 1.183-.5 2V21" />
          </svg>
        </a>
        <a href="https://www.linkedin.com/in/nick-moore-2258663b/" class="inline-block text-sm p2 leading-none bg-steel-300 rounded text-white hover:text-teal-500 hover:bg-coral-500 mt-4 lg:mt-0">
          <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-linkedin" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z"/>
            <rect x="4" y="4" width="16" height="16" rx="2" />
            <line x1="8" y1="11" x2="8" y2="16" />
            <line x1="8" y1="8" x2="8" y2="8.01" />
            <path d="M12 16v-5" />
            <path d="M16 16v-3a2 2 0 0 0 -4 0" />
          </svg>
        </a>
        <a href="https://codepen.io/nmoore1407/#" class="inline-block text-sm p2 leading-none bg-steel-300 rounded text-white hover:text-teal-500 hover:bg-coral-500 mx-2 mt-4 lg:mt-0">
          <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-codepen" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#2c3e50" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path stroke="none" d="M0 0h24v24H0z"/>
            <path d="M3 15l9 6l9 -6l-9 -6l-9 6" />
            <path d="M3 9l9 6l9 -6l-9 -6l-9 6" />
            <line x1="3" y1="9" x2="3" y2="15" />
            <line x1="21" y1="9" x2="21" y2="15" />
            <line x1="12" y1="3" x2="12" y2="9" />
            <line x1="12" y1="15" x2="12" y2="21" />
          </svg>
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data () {
    return {
      isOpen: false
    }
  }
}
</script>

<style scoped>
  nav {
    z-index: 100;
  }
</style>
