<template>
  <NavBar />
  <div class="nav-buttons">
    <button class="button" @click="back">Go back</button>
    <button class="button" @click="forward">Go forward</button>
  </div>

  <router-view />
</template>
<script>
import NavBar from "@/components/NavBar.vue";

export default {
  components: { NavBar },
  methods: {
    back() {
      this.$router.go(-1);
    },
    forward() {
      this.$router.go(1);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
}
.nav-buttons {
  display: flex;
  justify-content: space-around;
}
.button {
  background-color: aqua;
  color: #2c3e50;
  padding: 15px;
  border-radius: 20px;
  border: none;
}
</style>
