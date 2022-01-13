<template>
    <main>
        <div class="my_container">
              <!-- FILM -->
            
            <div class="content_list">
                <div class="row row-cols-lg-6">
                    <SingleCard v-for="(movie,index) in responseMoviesArray" :key="index"  :filmCard="movie"/>
                </div>
            </div>

            <!-- SERIE TV -->
            
            <div class="content_list">
                <div class="row row-cols-lg-6">
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
    height:100vh;
    background-color: black;

    .content_list{

        padding: 30px;

    }
}




</style>