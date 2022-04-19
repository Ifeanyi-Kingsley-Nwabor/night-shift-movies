<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <!-- <router-link>
        <h2>{{ movie.title }}</h2>
      </router-link> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      movies: [],
    };
  },

  // created() {
  //   const url = "http://www.omdbapi.com/?apikey=7c985542";
  // },

  mounted() {
    const url = "http://www.omdbapi.com/?apikey=7c985542";

    async function getMovies() {
      try {
        let response = await fetch(url);
        console.log("my movies " + response);
        this.movies = response.json();
      } catch (err) {
        console.error(err);
        // Handle errors here
      }
    }
    getMovies();
  },
};
</script>

<style>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
