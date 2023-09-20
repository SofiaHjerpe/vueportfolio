
<template>
  <body>
    <nav>
      
      <div class="branding">
        <h1 class="logo">Sofia Hjerpe</h1>
         <p class="logo-text"> Junior Frontend developer and UX/UI designer</p>
     </div>
         
<div>
  <div class="menu" @click="toggleMobileView" v-show="mobile" >
    <div :class="{'line1':mobileNav}"></div>
    <div :class="{'line2':mobileNav}"></div>
    <div :class="{'line3':mobileNav}"></div>
  </div>
</div>
<transition name="mobile-nav">
  <ul v-show="mobileNav" class="mobileN" >
    <li><router-link to="/">Home</router-link></li>
    <li><router-link  to="/about">About</router-link></li>
    <li><router-link  to="/projects">Projects</router-link></li>
      
</ul>

</transition>

<ul v-show="!mobile" class="nav-links">
  <li><router-link to="/">Home</router-link></li>
  <li><router-link  to="/about">About</router-link></li>
  <li><router-link  to="/projects">Projects</router-link></li>
</ul> 

</nav>

 <div @click="removeMobileView" style="display:flex; justify-content: space-around">
  
  <router-view> 
  
  </router-view>
</div>
</body>
</template>
<script>
import { RouterLink, RouterView } from 'vue-router'
export default {
  name: 'app',
  data(){
    return {
    mobile: false,
    mobileNav: null, 
    windowWidth: null, 
  }
  }, 
 
  created() {
    window.addEventListener("load", this.checkScreen);

    window.addEventListener("resize", this.checkScreen);
  },

 
  methods: {
    toggleMobileView() {
      this.mobileNav = !this.mobileNav
    },  
    removeMobileView() {
      if(this.mobileNav == true ){
      return this.mobileNav = false
    }else {
      return this.mobileNav = false
    }
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if(this.windowWidth <= 750){
        this.mobile = true
        return;
      }
      this.mobile = false;
      this.mobileNav = false;

    }

  }
}
</script>

