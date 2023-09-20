<template>
    <div class="project-item" style="margin-top: 30px">
        <h4 class="project-heading" >{{title}} </h4>
        <p class="project-description">Description: {{description }}</p>
        <span class="project-link">Link: &nbsp; <a :href="plink">Link </a> </span>
    
        <span class="list-wrap">
          Languages: &nbsp; 
          <div class="list-of-languages">
            {{languages }}
        </div>
        </span>
    
    <div class="image-item" style="align-self: center">
          
      <img  class="moblieImage" :src="imageOne"/>
      <img  class="moblieImage" :src="imageTwo"/>

      <img class="moblieImage" :src="imageThree"/>
      <img  class="moblieImage" :src="imageFour"/>

</div>

    
    <button>
      <router-link
        :to="{ name: 'projects'}"> 
        Go back
      </router-link>
     </button>
    </div>
 
</template>
<script>
import data from "./../data.js";
export default {
  data() {
    return {
      project: data.projects,
      title: "",
      description: "",
      plink: "",
      languages: "",
      imageOne: "",
      imageTwo: "",
      imageThree: "",
      imageFour: "",
    }
  },
  mounted() {
    const id = this.$route.params.id;
    const project = this.project.find(project => project.id == id);
    this.title = project.title;
    this.description = project.description;
    this.plink = project.plink;
    this.languages = project.languages;
    this.imageOne = project.imageOne;
    this.imageTwo = project.imageTwo;
    this.imageThree = project.imageThree;
    this.imageFour = project.imageFour;

  }, 

}
</script>