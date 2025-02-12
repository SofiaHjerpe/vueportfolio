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
    <SocialMediaItem />
  </div>
</template>
<script>
import SocialMediaItem from "./SocialMediaItem.vue";

export default {
  name: "about",
  components: {
    SocialMediaItem,
  },
  data() {
    return {
      mobile: false,
      windowWidth: null,
    };
  },

  created() {
    window.addEventListener("load", this.checkScreen);
    window.addEventListener("resize", this.checkScreen);
  },

  methods: {
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
    },
  },
};
</script>


