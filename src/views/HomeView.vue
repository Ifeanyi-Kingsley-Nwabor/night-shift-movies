<template>
  <div class="home">
    <AllMovies msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import AllMovies from "@/components/AllMovies.vue";

export default {
  name: "HomeView",
  components: {
    AllMovies,
  },
};
</script>
