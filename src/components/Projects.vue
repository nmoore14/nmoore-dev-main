<template>
  <div class="relative flex flex-col w-full p-4 bg-white">
    <h1 class="w-full font-display text-3xl text-center">Projects</h1>
    <div class="relative flex flex-row flex-wrap w-full justify-center">
      <ProjectCard
        v-for="(project, index) in projectList"
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
      projectList: projects
    }
  }
}
</script>
