<template>
  <div id="app">
    <header>
      <Header @performSearch="searchMovie"/>
    </header>
    
    
    <main >
      <Main  :infoMovie="moviesList" :infoSerie="seriesList" :infoActors="actorsList"/>
    </main>
    
    
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
      // APIUrlActor:"https://api.themoviedb.org/3/search/person?api_key=4be4eac11184cea75c396dce4c83f5b5&query=",
      moviesList: [],
      seriesList: [],
      // actorsList: [],
      searchText: "Fast",
    }
  },
  created() {
    this.getMovies();
    this.getSerieTv();
    // this.getActors();
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
    // getActors() {
    //     axios
    //     .get(this.APIUrlActor+this.moviesList.id)
    //     .then( result => {
          
    //       this.actorsList = result.data.results;
    //       console.log(this.actorsList);
    //     })
    // },
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

header {
  position: relative;
}

</style>
