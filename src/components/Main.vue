<template>
<div class="container">
  <div class="row">
    <ul v-for="(inf, index) in info" :key="index">
      <li>
        <Card :key="index" :dati="inf"/>
      </li>
    </ul>
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


</style>
