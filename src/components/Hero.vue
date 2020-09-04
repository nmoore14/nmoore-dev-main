<template>
  <div class="absolute w-full bg-sand-500" id="hero-main">
    <div class="hidden md:block">
      <!--Should not see on small screens -->
      <div id="desktop-display" class="w-full h-full">
        <div id="desktop-content" class="absolute w-1/2 bottom-0 right-0 mb-4 bg-steel-100">
          <div id="content-display" class="absolute w-5/6 h-full bottom-0 right-0 pr-4">
            <h1 class="text-right font-display text-5xl font-thin text-steel-500">Web Developer</h1>
            <h1 class="text-right font-display text-5xl font-thin text-steel-500">Graphic Designer</h1>
          </div>
        </div>
      </div>
    </div>
    <div class="block md:hidden">
      Should not see on larger screens
    </div>
  </div>
</template>

<script>
export default {
  name: 'Hero'
}
</script>

<style scoped>
  #hero-main {
    height: 30rem;
  }

  #desktop-content {
    height: 20rem;
    clip-path: polygon(25% 0%, 100% 0%, 100% 100%, 0% 100%);
  }
</style>
