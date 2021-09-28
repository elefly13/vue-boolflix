<template>
  <div id="app">
    <Header @performSearch="searchMovie"/>
    <div class="box_container">
    <div  >
      <Main  :infoMovie="moviesList" :infoSerie="seriesList"/>
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
      APIUrlTV: "https://api.themoviedb.org/3/search/tv?api_key=4be4eac11184cea75c396dce4c83f5b5&query=",
      moviesList: [],
      seriesList: [],
      searchText: "Fast",
    }
  },
  created() {
    this.getMovies();
    this.getSerieTv();
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
    getSerieTv() {
      axios
        .get(this.APIUrlTV+this.searchText)
        .then( result => {
          
          this.seriesList = result.data.results;
          console.log(this.seriesList);
        })
    },
    searchMovie(text) {
      
      this.searchText = text;
      console.log(this.searchText);
      this.getMovies();
      this.getSerieTv();
    }
    
  }
}
</script>

<style lang="scss">
@import "./style/general.scss";
@import "./style/vars.scss";

</style>
