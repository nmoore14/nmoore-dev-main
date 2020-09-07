<template>
  <div id="card"
    class="flex flex-col transform hover:scale-105 cursor-pointer"
    @mouseenter="isVisible = !isVisible"
    @mouseleave="isVisible = !isVisible"
  >
    <div class="max-w-sm rounded m-2 bg-steel-100 overflow-hidden shadow-lg">
      <div
        v-if="hasLinks"
        class="w-full relative flex flex-row self-center justify-around overflow-hidden rounded shadow-lg z-10 linkContainer"
        :class="isVisible ? 'isVisible' : 'hide'"
      >
        <a v-for="(link, index) in links" :key="index"
          class="w-2/3 font-body text-xl text-white font-bold p-2 m-2 rounded bg-steel-500 opacity-75 hover:opacity-100"
          :href=link.url
          target="_blank"
        >
          {{ link.title }}
        </a>
      </div>
      <img class="w-full" :src="`${publicPath}${image}`" alt="Sunset in the mountains">
      <div class="px-6 py-4">
        <div class="font-display font-bold text-xl mb-2">{{ title }}</div>
        <p class="font-body text-grey-900 text-base">
          {{ shortDescription }}
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span
          class="inline-block bg-gray-200 rounded px-3 py-1 font-body text-sm font-semibold text-gray-700 mr-2 mb-2 hover:bg-coral-500 hover:text-white cursor-pointer"
          v-for="(tag, index) in tags"
          :key="index"
        >
          #{{ tag }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    title: String,
    image: String,
    shortDescription: String,
    links: Array,
    tags: Array
  },
  data () {
    return {
      publicPath: process.env.BASE_URL,
      isVisible: false,
      hasLinks: false
    }
  },
  methods: {
    linkCheck () {
      if (this.links) {
        this.hasLinks = true
      }
    }
  },
  mounted () {
    this.linkCheck()
  }
}
</script>

<style scoped>
  .linkContainer {
    height: 3.5rem;
  }

  .hide {
    margin-top: -3.5rem;
    transition: ease-in-out .5s;
  }

  .isVisible {
    margin-top: 0;
    transition: ease-in-out .5s;
  }
</style>
