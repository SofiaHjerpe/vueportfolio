<template>
  <div class="project-container">
     <SingleProjectItem />
 </div>
</template>
<script>

import SingleProjectItem from "../components/SingleProjectItem.vue";
export default {
  name: 'SingleProjectView',
    components: {
       SingleProjectItem
    },
 
}
</script>