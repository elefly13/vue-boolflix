<template>
  <div id="app">
    <Header @performSearch="searchMovie"/>
    <div class="container">
      <div v-for="(movie, index) in moviesList" :key="index" class="row">
        <Main  :info="movie"/>
      </div>
    </div>
    
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      APIUrl: "https://api.themoviedb.org/3/search/movie?api_key=4be4eac11184cea75c396dce4c83f5b5&query=",
      moviesList: [],
      searchText: "Rick",
    }
  },
  created() {
    this.getMovies();
  },
 
  methods: {
    getMovies() {
      axios
        .get(this.APIUrl+this.searchText)
        .then( result => {
          
          this.moviesList = result.data.results;
          console.log(this.moviesList);
        })
    },
    searchMovie(text) {
      
      this.searchText = text;
      console.log(this.searchText);
      this.getMovies();
    }
    
  }
}
</script>

<style lang="scss">
@import "./style/general.scss";
@import "./style/vars.scss";

</style>
