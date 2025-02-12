
<template>
  <div class="project-container"> 
      <h1 class="heading" :style="!mobile ? 'margin-top: 6.25rem;margin-inline:0': 'margin-top: 6.25rem;margin-inline:1em 0'">Projects</h1>
      <div class="projects">
    
      <ProjectComponent :mobile="mobile"/>
     </div>
    </div>
</template>
<script>
import ProjectComponent from './ProjectComponent.vue'
export default {
  name: 'ProjectItem', 
  components: {
    ProjectComponent
  }, 
  props: {
    mobile: Boolean
  }
}

</script>