<template>
  <div id="app" class="flex flex-col">
    <Navbar/>
    <div id="content" class="absolute">
      <Hero/>
      <Projects/>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Projects from './components/Projects.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Hero,
    Projects
  }
}
</script>
