<template>
  <div>
 
    <div class="card">
      <div class="box_img">
        <img :src="imgSRC+dati.poster_path" alt="">
      </div>
    </div>

    <div class="card">
      <div class="box_dati">
        <li><h6>Titolo:</h6> {{dati.title}}{{dati.name}}</li>
        <li><h6>Titolo originale:</h6>{{dati.original_title}}{{dati.original_name}}</li>
        <li class="flag">
          <img :src="require('../assets/img/'+ dati.original_language + '.png')" >
        </li>
        <!-- <li v-else>{{dati.original_language}}</li> -->
        <li ><h6>Voto:</h6> 
          <i  v-for="index in Math.ceil(dati.vote_average / 2)" :key="index" class="fas fa-star"></i>{{dati.vote_average}}
        </li>
        <li><h6>Overview: </h6>{{dati.overview}}</li>
      </div>
    </div>
  </div>

  
</template>

<script>
export default {
  name: 'Card',
  props: ['dati'],

  data() {
    return {
      imgSRC: "https://image.tmdb.org/t/p/w342",
      
    }
    
  },


}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/general.scss";
@import "../style/vars.scss";
.card {
  width: 342px;
  height: 513px;
    .box_img {
      width: 342px;
      height: 513px;
      border: 1px solid $terzo;
        img {
          width: 100%;
          height: 100%;
        }
    }
}
.box_dati {
  width: 342px;
  height: 513px;
  padding: 50px 30px;
  background-color: $secondo;
  border: 1px solid $terzo;
  overflow: auto;
    li {
      list-style: none;
      color: $terzo;
      font-family: Arial, Helvetica, sans-serif;
      padding: 5px;
    }
    .flag {
      width: 40px;
      height: 40px;
        img {
          width: 100%;
        }
    }
    h6 {
      display: inline-block;
      padding-right: 5px;
    }
    i {
      color: gold;
    }
}


</style>
