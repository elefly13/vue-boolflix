<template>
<div>
  <div class="box ">
    <div class="line ">
      <a href="/">
      <h1>BOOLFLIX</h1>
      </a>
      
      <div class="cerca">
        <input 
          type="text"
          placeholder="Cerca ..."
          v-model="inputText"
          @keyup.enter="$emit('performSearch', inputText)"
        >
        <button
          type="submit"
          @click.prevent="$emit('performSearch', inputText)"
          >Cerca
        </button>
      </div>
    </div>
  </div>

</div>

  
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputText: '',
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/general.scss";
@import "../style/vars.scss";

.box {
  position: relative;
  top: 0;
  width: 100vw;
  height: 10vh;
  background-color: $secondo;
    .line {
      
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 130px;
      padding: 0 50px;
        a {
          text-decoration: none;
            h1 {
              color: red;
            }
        }
        
    }
}

</style>
