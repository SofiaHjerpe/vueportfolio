<template>
  <div class="home-view">
    <h3 class="heading" style="margin-top: 6.25rem; margin-bottom: 0">
      Hi and welcome!
    </h3>
    <div :class="!mobile ? 'about flex-container' : 'about m-container'">
      <p :class="!mobile ? 'the-welcome-text' : 'home-text'">
        My name is Sofia Hjerpe. Go to "About" to read more About me.
      </p>
      <img class="image" src="../assets/images/me.jpg" />
    </div>
    <SocialMediaItem :mobile="mobile" />
  </div>
</template>

<script>
import SocialMediaItem from "./SocialMediaItem.vue";

export default {
  name: "/",
  components: {
    SocialMediaItem,
  },
 props: {
  mobile: {
    type: Boolean,
    required: true,
  },
},
watch: {
  mobile(newVal) {
    console.log("Mobile state changed:", newVal);
  },
},
};
</script>


