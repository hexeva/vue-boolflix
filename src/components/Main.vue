<template>
    <main>
        <div class="container">
            <!-- FILM -->
            <h2>ALL MOVIES </h2>
            <div class="movie_list">
                <div class="row row-cols-lg-5">
                    <SingleCard v-for="(movie,index) in responseMoviesArray" :key="index"  :filmCard="movie"/>
                </div>
            </div>

            <!-- SERIE TV -->
            <h2>ALL TV SERIES</h2>

            <div class="series_list">
                <div class="row row-cols-lg-5">
                    <SingleCard v-for="(show,index) in responseSeriesArray" :key="index"  :seriesCard="show"/>
                </div>
            </div>
            
            

        </div>
        
    </main>
        
   
    
</template>

<script>
 import SingleCard from "./SingleCard.vue";

export default {
    name:'Main',

    components:{
        SingleCard,
    },

    props:{
        responseMoviesArray:Array,
        responseSeriesArray:Array,
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';




</style>