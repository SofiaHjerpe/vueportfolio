

<template>
  <main>
    <HomeItem :mobile="mobile"/>
  </main>
</template>
<script>
import HomeItem from "../components/HomeItem.vue";

export default {
  name: "HomeView",
  components: {
    HomeItem,
  },
  props: {
    mobile: Boolean,
  },
};
</script>

