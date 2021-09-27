<template>
<div class="box_container">
  <div class="bigbox_card">
    <div class="box_card" v-for="(inf, index) in info" :key="index">
      
        <Card :key="index" :dati="inf"/>
      
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
  props: ['info']
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.box_container {
  width: 100vw;
  height: 90vh;
  margin: auto;
    .bigbox_card {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      width: 100%;

    }
}


</style>
