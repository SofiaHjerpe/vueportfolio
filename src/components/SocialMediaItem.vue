<template>
  <div :style="mobile ? 'margin-inline: 5em 0': ''">
    <h3 class="heading" style="margin-inline: 0; white-space: nowrap">
      Social media
    </h3>
    <div class="icons">
      <a href="https://www.facebook.com/sofia.hjerpe.9/">
        <img class="icon1" src="../assets/images/facebook.png"
      /></a>

      <a href="https://www.linkedin.com/in/sofia-hjerpe-17b171178/">
        <img class="icon2" src="../assets/images/linkedin.png" />
      </a>
      <a href="https://github.com/SofiaHjerpe">
        <img class="icon3" src="../assets/images/github.png" />
      </a>
    </div>
  </div>
</template>
<script>

export default {
  name: "socialmedia",
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


