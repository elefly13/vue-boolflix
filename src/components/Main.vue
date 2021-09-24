<template>
<div>
  <div class="card">
    <h3>{{info.title}}</h3>
    <h3>{{info.original_title}}</h3>
    <h3>{{info.original_language}}</h3>
    <h3>{{info.vote_average}}</h3>
  </div>
</div>

  
</template>

<script>
export default {
  name: 'Main',
  props: ['info']
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">


</style>
