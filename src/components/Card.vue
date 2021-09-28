<template>
  <div class="flip_card">
    <div class="card flip_card_inner">
      <div class="box_img flip_card_front">
        <img v-if="item.poster_path" :src="imgSRC + item.poster_path" />
        <img v-else :src="require('../assets/img/poster_placeholder.png')" />
      </div>

      <div class="card flip_card_back">
        <div class="box_dati">
          <ul>
            <li>
              <h6>Titolo:</h6>
              {{ item.title ? item.title : item.name }}
            </li>
            <li>
              <h6>Titolo originale:</h6>
              {{
                item.original_title ? item.original_title : item.original_name
              }}
            </li>
            <li class="flag">
              <img
                :src="
                  require('../assets/img/' + item.original_language + '.png')
                "
              />
              <!-- <img v-if="imageFlag.includes(item.original_language)" :src="require('../assets/img/'+ item.original_language + '.png')" >
            <p v-else>{{item.original_language}}</p> -->
            </li>
            <li>
              <h6>Voto:</h6>
              <!-- primo metodo con solo stelline vuote -->
              <!-- <i  v-for="index in Math.ceil(item.vote_average / 2)" :key="index" class="fas fa-star"></i> -->
              <i
                v-for="n in 5"
                :key="n"
                :class="n <= getVote() ? 'fas' : 'far'"
                class="fa-star"
              ></i>
            </li>
            <li>
              <h6>Overview:</h6>
              {{ item.overview ? item.overview : item.overview }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["item"],

  data() {
    return {
      imgSRC: "https://image.tmdb.org/t/p/w342",
      imageFlags: ["it", "de", "en", "fr", "sp"],
    };
  },
  methods: {
    getVote() {
      return Math.ceil(this.item.vote_average / 2);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/general.scss";
@import "../style/vars.scss";

.flip_card {
  background-color: transparent;
  width: 342px;
  height: 513px;
  border: 1px solid $terzo;
  // perspective: 1000px;
}
.flip_card:hover .flip_card_inner{
  transform: rotateY(180deg);
}
.flip_card_inner {
    position: relative;
    width: 342px;
    height: 513px;
    transition: transform 0.8s;
    transform-style: preserve-3d;
}
.flip_card_front {
      position: absolute;
      top: 0;
      left: 0;
      width: 342px;
      height: 513px;
      z-index: 999;
      backface-visibility: hidden;
}
 .flip_card_front img {
  width: 100%;
  height: 100%;
}
 .flip_card_back {
      position: absolute;
      width: 342px;
      height: 513px;
      backface-visibility: hidden;
      padding: 40px 20px;
      background-color: $secondo;
      border: 1px solid $terzo;
      overflow: auto;
      transform: rotateY(180deg);
 }
 li {
        list-style: none;
        color: $terzo;
        font-family: Arial, Helvetica, sans-serif;
        padding-top: 10px;
 }
 .flag {
          width: 40px;
          height: 40px;
 }
 .flag img {
    width: 100%;
    height: 100%;
  }
  h6 {
    display: inline-block;
    padding-right: 5px;
  }
  i {
    color: gold;
  }

// .flip_card:hover .flipcard_inner{
//   transform: rotateY(180deg);
// }
// .flip-card {
//   background-color: transparent;
//   width: 342px;
//   height: 513px;
//   border: 1px solid $terzo;
//   perspective: 1000px;
  
//   .flip_card_inner {
//     position: relative;
//     width: 342px;
//     height: 513px;
//     transition: transform 0.8s;
//     transform-style: preserve-3d;
//     .flip_card_front {
//       position: absolute;
//       top: 0;
//       left: 0;
//       width: 342px;
//       height: 513px;
//       backface-visibility: hidden;
//       background-color: violet;
//       img {
//         width: 100%;
//         height: 100%;
//       }
//     }
    
//     .flip_card_back {
//       position: absolute;
//       top: 0;
//       left: 0;
//       width: 342px;
//       height: 513px;
//       backface-visibility: hidden;
//       padding: 50px 30px;
//       background-color: $secondo;
//       border: 1px solid $terzo;
//       overflow: auto;
//       transform: rotateY(180deg);
//       li {
//         list-style: none;
//         color: $terzo;
//         font-family: Arial, Helvetica, sans-serif;
//         padding-top: 10px;
//         &.flag {
//           width: 40px;
//           height: 40px;
//           img {
//             width: 100%;
//           }
//         }
//         h6 {
//           display: inline-block;
//           padding-right: 5px;
//         }
//         i {
//           color: gold;
//         }
//       }
//     }
//   }
// }


// .card {
//   width: 342px;
//   height: 513px;
//     .box_img {
//       width: 342px;
//       height: 513px;
//       border: 1px solid $terzo;
//         img {
//           width: 100%;
//           height: 100%;
//         }
//     }
//   }

// .box_dati {

//   width: 342px;
//   height: 513px;
//   padding: 50px 30px;
//   background-color: $secondo;
//   border: 1px solid $terzo;
//   overflow: auto;
//     li {
//       list-style: none;
//       color: $terzo;
//       font-family: Arial, Helvetica, sans-serif;
//       padding-top: 10px;
//     }
//     .flag {
//       width: 40px;
//       height: 40px;
//         img {
//           width: 100%;
//         }
//     }
//     h6 {
//       display: inline-block;
//       padding-right: 5px;
//     }
//     i {
//       color: gold;
//     }

// }
</style>
