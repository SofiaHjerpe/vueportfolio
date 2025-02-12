<template>
  <body>
    <nav>
      <div class="branding">
        <h1 class="logo">Sofia Hjerpe</h1>
        <p class="logo-text">
          Frontend developer, developer and UX/UI designer
        </p>
      </div>

      <div>
        <div class="menu" @click="toggleMobileView" v-show="mobile">
          <div :class="{ line1: mobileNav }"></div>
          <div :class="{ line2: mobileNav }"></div>
          <div :class="{ line3: mobileNav }"></div>
        </div>
      </div>
      <transition name="mobile-nav">
        <ul v-show="mobileNav" class="mobileN">
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/projects">Projects</router-link></li>
        </ul>
      </transition>

      <ul v-show="!mobile" class="nav-links">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/projects">Projects</router-link></li>
      </ul>
    </nav>

    <div
      @click="removeMobileView"
      style="display: flex"
      :class="mobile ? 'mobileContainer' : 'container'"
    >
      <router-view :mobile="mobile"></router-view>
    </div>
  </body>
</template>

<script>
import { ref, onMounted, onUnmounted } from "vue";

export default {
  name: "app",
  setup() {
    const mobile = ref(window.innerWidth <= 750);
    const mobileNav = ref(false);

    const checkScreen = () => {
      mobile.value = window.innerWidth <= 750;
    };

    const toggleMobileView = () => {
      mobileNav.value = !mobileNav.value;
    };

    const removeMobileView = () => {
      mobileNav.value = false;
    };

    onMounted(() => {
      window.addEventListener("resize", checkScreen);
    });

    onUnmounted(() => {
      window.removeEventListener("resize", checkScreen);
    });

    return {
      mobile,
      mobileNav,
      toggleMobileView,
      removeMobileView,
    };
  },
};
</script>

