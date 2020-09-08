<template>
  <div class="relative w-full bg-sand-500 mt-8" id="hero-main">
    <div class="hidden md:block w-full">
      <!--Should not see on small screens -->
      <div id="desktop-display" class="w-full h-full">
        <div id="desktop-image" class="absolute w-1/2 bottom-0 left-0 ml-4 mb-4 bg-steel-100">
          <img src="@/assets/images/nick-style.png" alt="Image of Nick Moore" class="w-full object-cover -mt-24">
        </div>
        <div id="desktop-content" class="absolute w-1/2 bottom-0 right-0 mr-4 mb-4 bg-steel-100">
          <div id="content-display" class="absolute w-5/6 h-full bottom-0 right-0 pr-4">
            <h1 class="text-right font-display text-5xl font-thin text-steel-500">Web Developer</h1>
            <h1 class="text-right font-display text-5xl font-thin text-steel-500">Graphic Designer</h1>
          </div>
        </div>
      </div>
    </div>
    <div class="block md:hidden">
      <div id="mobile-display" class="absolute flex flex-col w-full">
        <div id="mobile-image" class="relative w-full">
          <img src="@/assets/images/nick-style.png" alt="Image of Nick Moore" class="w-full">
        </div>
        <div id="mobile-content" class="relative">
          <div id="mobile-content-display" class="w-full">
            <h1 class="text-center font-display text-2xl font-thin text-steel-500">Web Developer</h1>
            <h1 class="text-center font-display text-2xl font-thin text-steel-500">Graphic Designer</h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Hero',
  publicPath: process.env.BASE_URL
}
</script>

<style scoped>
  #hero-main {
    height: 30rem;
    z-index: 10;
  }

  #desktop-image {
    height: 85%;
    clip-path: polygon(0 1%, 100% 0%, 85% 100%, 0% 100%);
  }

  #desktop-content {
    height: 85%;
    clip-path: polygon(15% 0%, 100% 0%, 100% 100%, 0% 100%);
  }
</style>
