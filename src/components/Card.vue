<template>
<div>
  <div class="card">
    <li>{{dati.title}}</li>
    <li>{{dati.original_title}}</li>
    <li>{{dati.original_language}}</li>
    <li>{{dati.vote_average}}</li>
  </div>
</div>

  
</template>

<script>
export default {
  name: 'Card',
  
  props: ['dati']
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">


</style>
