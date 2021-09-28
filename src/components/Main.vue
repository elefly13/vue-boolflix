<template>
<div class="box_container">
  <div class="bigbox_card">
   
    <div class="box_card" v-for="(infoM) in infoMovie" :key="infoM.id">
      
        <Card :key="infoM.id" :item="infoM"  />
      
    </div>
    <div class="box_card" v-for="(infoS) in infoSerie" :key="infoS.id">
      
        <Card :key="infoS.id"  :item="infoS" />
      
    </div>
  </div>
</div>

  
</template>

<script>
import Card from './Card.vue'
export default {
  name: 'Main',
  components: {
    Card
    
  },
  props: ['infoMovie', 'infoSerie']
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.box_container {
  width: 100vw;
  min-height: 90vh;
  margin: auto;
    .bigbox_card {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      width: 100%;
      height: 100%;

    }
}


</style>
