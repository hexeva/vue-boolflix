<template>
    <section>
        <div class="card_list">
            <SingleCard v-for="(movie,index) in responseMoviesArray" :key="index" :filmCard="movie"/>
            
        </div>
    </section>
    
</template>

<script>
 import SingleCard from "./SingleCard.vue";

export default {
    name:'Main',

    components:{
        SingleCard,
    },

    props:{
        responseMoviesArray:Object,
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
.card_list{
    display: flex;
    flex-wrap: wrap;

}



</style>