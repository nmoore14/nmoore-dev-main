<template>
  <div class="relative flex flex-col w-full p-4 bg-white" id="projects">
    <h1 class="flex flex-row w-full justify-center items-center font-display text-3xl text-center">
      Projects
      <span>
        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-filter ml-2 hover:bg-steel-500 cursor-pointer rounded"
        :class="{'filtering': filtering, 'filtered': filtered}"
        @click="filtering = !filtering"
        width="30" height="30" viewBox="0 0 24 24" stroke-width="1.5" :stroke="filtered ? '#ffffff' : '#c5c5c5'" fill="none" stroke-linecap="round" stroke-linejoin="round">
          <path stroke="none" d="M0 0h24v24H0z"/>
          <path d="M5.5 5h13a1 1 0 0 1 0.5 1.5L14 12L14 19L10 16L10 12L5 6.5a1 1 0 0 1 0.5 -1.5" />
        </svg>
      </span>
    </h1>
    <div v-if="filteredList.length > 0"
      class="relative flex flex-row flex-wrap w-full justify-center self-center mb-4"
    >
      <div class="relative w-auto justify-center self-center">
        <p
          class="w-64 p-2 bg-steel-100 font-body text-lg text-steel-300 text-center rounded-md cursor-pointer"
          @click="clearFilteredList()"
        >
          Remove All
        </p>
      </div>
      <div v-for="(tag, index) in filteredList" :key="index"
        class="transform w-1/2 sm:w-1/5 p-2 cursor-pointer"
        @click="removeFilter(index)"
      >
        <p class="w-full p-2 bg-coral-500 font-body text-lg text-white rounded-md">{{ tag }} <span class="float-right">x</span></p>
      </div>
    </div>
    <div v-if="filtering"
      class="relative flex flex-row flex-wrap w-auto self-center mb-4"
    >
      <div v-for="(filter, index) in filterList" :key="index"
        class="transform w-1/2 sm:w-1/3 p-2 cursor-pointer"
        @click="filterProjects(filter)"
      >
        <p class="w-full p-2 bg-steel-100 font-body text-lg text-steel-500 hover:scale-105 hover:bg-steel-300 hover:text-black rounded-md">{{ filter }}</p>
      </div>
    </div>
    <div class="relative flex flex-row flex-wrap w-full justify-center">
      <ProjectCard
        v-for="(project, index) in displayList"
        :key="index"
        :title="project.title"
        :image="project.image"
        :shortDescription="project.shortDescription"
        :links="project.links"
        :tags="project.tags"
      />
    </div>
  </div>
</template>

<script>
import ProjectCard from './cards/ProjectCard.vue'
import { projects } from '../assets/data/projects'

export default {
  name: 'Projects',
  components: {
    ProjectCard
  },
  data () {
    return {
      projectList: projects,
      displayList: [],
      filterList: [],
      filteredList: [],
      filtering: false,
      filtered: false
    }
  },
  methods: {
    buildFilterList () {
      const tempList = []
      for (let i = 0; i < this.projectList.length; i++) {
        for (let j = 0; j < this.projectList[i].tags.length; j++) {
          tempList.push(this.projectList[i].tags[j])
        }
      }
      this.filterList = [...new Set(tempList)]
    },
    createDisplayList () {
      if (!this.filtered) {
        this.displayList = this.projectList
      }
    },
    filterProjects (tag) {
      const tempList = []

      if (!this.filteredList.includes(tag)) {
        this.filteredList.push(tag)
      }

      for (let y = 0; y < this.filteredList.length; y++) {
        for (let i = 0; i < this.projectList.length; i++) {
          for (let j = 0; j < this.projectList[i].tags.length; j++) {
            if (this.projectList[i].tags[j] === this.filteredList[y]) {
              tempList.push(this.projectList[i])
            }
          }
        }
      }

      this.displayList = tempList
      this.displayList = [...new Set(this.displayList)]
      this.filtered = true
    },
    clearFilteredList () {
      this.filteredList = []
      this.filtered = false
    },
    removeFilter (index) {
      this.filteredList.splice(index, 1)
      if (!this.filteredList.length) {
        this.filtered = false
      } else {
        this.rebuildFilter()
      }
    },
    rebuildFilter () {
      const tempList = []
      for (let y = 0; y < this.filteredList.length; y++) {
        for (let i = 0; i < this.projectList.length; i++) {
          for (let j = 0; j < this.projectList[i].tags.length; j++) {
            if (this.projectList[i].tags[j] === this.filteredList[y]) {
              tempList.push(this.projectList[i])
            }
          }
        }
      }

      this.displayList = tempList
      this.displayList = [...new Set(this.displayList)]
    }
  },
  mounted () {
    this.buildFilterList()
    this.createDisplayList()
  },
  watch: {
    filtered: function () {
      if (!this.filtered) {
        this.createDisplayList()
      }
    }
  }
}
</script>

<style scoped>
  .filtering {
    @apply bg-steel-500;
  }

  .filtered {
    @apply bg-coral-500;
  }
</style>
