
<template>
  <div
    :style="!mobile ? '  margin-inline: 1em 0;' : 'margin-inline: 20px'"
    class="project-item"
    v-for="t in sorted_projects"
    :key="t"
  >
    <h4 class="project-heading">{{ t.title }}</h4>
    <p class="project-description">Description: {{ t.description }}</p>
    <span class="project-link">Link: &nbsp; <a :href="t.plink">Link </a></span>

    <div class="list-wrap">
      Languages: &nbsp;
      <div class="list-of-languages">
        {{ t.languages }}
      </div>
    </div>

    <div class="image-item" style="align-self: center">
      <img class="moblieImage" :src="t.imageOne" />
      <img class="moblieImage" :src="t.imageTwo" />

      <img class="moblieImage" :src="t.imageThree" />
      <img class="moblieImage" :src="t.imageFour" />
    </div>

    <button>
      <router-link
        :to="{ name: 'project', params: { id: t.id, mobile} }"
      >
        View project
      </router-link>
    </button>
  </div>
</template>
<script>
import data from "../data.js";
export default {

  data() {
    return {
      projects: data.projects,
      mobile: Boolean
    };
  },
  computed: {
    sorted_projects() {
      return this.projects.sort((a, b) => {
        return b.id - a.id;
      });
    },
  },
};
</script>
