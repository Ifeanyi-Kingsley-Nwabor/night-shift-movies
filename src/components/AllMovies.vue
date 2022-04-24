<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <!-- <router-link> -->
      <h2>{{ movies }}</h2>
      <!-- </router-link> -->
    </div>
  </div>
</template>

<script>
import { reactive } from "vue";
export default {
  name: "AllMovies",
  props: {
    msg: String,
  },
  data() {
    return {
      movies: [],
    };
  },
  setup() {
    // created() {
    const url =
      "https://api.themoviedb.org/3/search/movie?api_key=033b9feb10f6fc139ba6faa28567dfcf&query=Jack+Reacher";
    // const url =
    // "https://api.themoviedb.org/3/movie/157336?api_key=033b9feb10f6fc139ba6faa28567dfcf&append_to_response=videos,images";
    // const url = "http://www.omdbapi.com?apikey=7c985542";

    // Simple GET request using fetch
    const searchMovies = async () => {
      // const response = await fetch(`${url}&s=${title}`);
      const response = await fetch(`${url}`);
      const data = await response.json();
      this.movies = reactive(data);
      console.log("my movies " + this.movies);
    };
    searchMovies();
  },
  //   .then((response) => response.json())
  //   .then((data) => (this.movies = data.Title));
  // console.log("my movies " + this.movies);
  // },

  // mounted() {
  // const url = "http://www.omdbapi.com/?apikey=7c985542";

  // async function getMovies() {
  //   try {
  //     let response = await fetch(url);
  //     console.log("my movies " + response);
  //     this.movies = response.json();
  //   } catch (err) {
  //     console.error(err);
  //     // Handle errors here
  //   }
  // }
  // getMovies();
  // },
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
