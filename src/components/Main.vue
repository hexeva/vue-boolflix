<template>
    <main>
        <div class="my_container">
            <!-- FILM -->
            
            <div class="movie_list">
                <div class="row row-cols-lg-5">
                    <SingleCard v-for="(movie,index) in responseMoviesArray" :key="index"  :filmCard="movie"/>
                </div>
            </div>

            <!-- SERIE TV -->
            

            <div class="series_list">
                <div class="row row-cols-lg-5">
                    <SingleCard v-for="(show,index) in responseSeriesArray" :key="index"  :filmCard="show"/>
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
@import '../style/variables.scss';
@import '../style/general.scss';

main{
    width:100%;
    height:100%;
    background-color: black;
}




</style>