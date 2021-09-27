<template>
<div>
  <div class="card">
    <li>{{dati.title}}{{dati.name}}</li>
    <li>{{dati.original_title}}{{dati.original_name}}</li>
    <li v-if="this.dati.original_language === this.flags.country">
      <img :src="flags.flag" :alt="flags.country">
    </li>
    <li v-else>{{dati.original_language}}</li>
    <li>{{dati.vote_average}}</li>
  </div>
</div>

  
</template>

<script>
export default {
  name: 'Card',
  props: ['dati'],

  data() {
    return {
        flags: [
        {
          country: "en",
          flag: "../img/en.png"
        },
        {
          country: "it",
          flag: "../img/it.png"
        },
        {
          country: "de",
          flag: "../img/de.jpeg"
        },
        {
          country: "fr",
          flag: "../img/fr.jpeg"
        },
        
      ]
    }
    
  },

  // methods: {
  //   getFlag() {
  //     this.dati.original_language.map(element => {
  //       if (element === this.flags.country) {
  //         return this.flags.flag;

  //       } else {
  //         return this.dati.original_language;
  //       } 
  //     })
     
  //   }
    
  // }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">


</style>
