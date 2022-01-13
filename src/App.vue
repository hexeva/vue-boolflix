<template>
  <div id="app">
    <Header @research="allResearch" />
    <Main :responseMoviesArray="movieList" :responseSeriesArray="seriesList"/>
  </div>
</template>

<script>
import axios from 'axios';

 import Header from "./components/Header.vue";
 import Main from "./components/Main.vue";




export default {
  name: "App",
  components: {
    Header,
    Main,
  },

  data:function(){
    return {

      movieList:[],
      seriesList:[],
      userResearch:'',
      apiKey:'3b8e65acb65bbd04677cf76f0c18bc6d',

    };
  },

methods:{

  // FUunzione di richiamo dell'emit generica per film e serie tv

  allResearch:function(text){
    this.userResearch = text;
    this.callMovies();
    this.callSeries();
    

  },

  // funzione di chiamata api per i movies

  callMovies: function(){
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params:{
                    api_key:this.apiKey,
                    query: this.userResearch,
                }
            })
            .then((response) => {
              // console.log(response.data.results)
                this.movieList = response.data.results
            });
        },
    // end callMovies

    // Funzione di chiamata api per TV SHOWS

    callSeries:function(){
      axios.get('https://api.themoviedb.org/3/search/tv', {
        params:{
          api_key:this.apiKey,
          query:this.userResearch,
        }
      })
      .then((response) =>{
        // console.log(response.data.results)
        this.seriesList = response.data.results
      });
    },
  // // end callSeries

  
},
// End methods




};
</script>

<style lang="scss">
@import './style/variables';
@import './style/general';



</style>
