<template>
  <div id="app" class="flex flex-col">
    <Navbar/>
    <Hero/>
    <Projects/>
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
