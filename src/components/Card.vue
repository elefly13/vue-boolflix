<template>
<div>
  <div class="card">
    <div class="box_img">
      <img :src="imgSRC+dati.poster_path" alt="">
    </div>
    <li>{{dati.title}}{{dati.name}}</li>
    <li>{{dati.original_title}}{{dati.original_name}}</li>
    <li class="flag">
      <img :src="require('../assets/img/'+ dati.original_language + '.png')" >
    </li>
    <!-- <li v-else>{{dati.original_language}}</li> -->
    <li >Voto: 
      <i  v-for="index in Math.ceil(dati.vote_average / 2)" :key="index" class="fas fa-star"></i>{{dati.vote_average}}
    </li>
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

.flag {
  width: 40px;
  height: 40px;
    img {
      width: 100%;
    }
}

</style>
