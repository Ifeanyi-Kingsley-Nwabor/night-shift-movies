<template>
  <nav>
    <router-link to="/">
      <img
        class="logo"
        alt="Night shift movie logo"
        src="../assets/movie.png"
      />
    </router-link>
    <h3 class="nsm">Night Shift Movies</h3>
    <div>
      <router-link :to="{ name: 'Home' }">Home</router-link> |
      <router-link :to="{ name: 'About' }">About</router-link> |
      <router-link :to="{ name: 'Login' }">Login</router-link> |
      <router-link :to="{ name: 'Premuim' }">Premuim</router-link>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style>
.logo {
  width: 100px;
}
nav {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #42b983;
}
.nsm {
  /* font-size: 15px; */
  font-weight: 900;
  color: #2c3e50;
}
</style>
