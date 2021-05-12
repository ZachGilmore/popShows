<template>
  <div id="app">
    <Navigation />
    <div class="container">
      <div class="row">
        <Card v-for="movie in movies.slice(0, 4)" v-bind:key=movie.id :movieobj=movie class="col-12 col-md-3"></Card>
      </div>
    </div>
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import Card from "./components/Card.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Navigation,
    Card,
  },
  data()
  {
    return{
      // movies:[
      //   {id:1, title:'Top Gun', overview:"A movie about fighter pilots", poster_path: "topgun.jpg"},
      //   {id:2, title:'The Matrix', overview:"A movie about fighter pilots", poster_path: "matrix.jpg"}
        
      // ]
      movies: ""
    }
  },
  mounted()
  {
    axios.get("https://api.themoviedb.org/3/tv/popular?api_key=cef7ecc04fe7078af61575957da191fb&language=en-US&page=1")
                .then( (response) =>{
                    this.movies = response.data.results;
                })
  }
};
</script>

<style>
</style>
