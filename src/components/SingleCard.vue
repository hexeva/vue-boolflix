<template>
    <div class="card">
        
        <img :src="`https://image.tmdb.org/t/p/w342/`+filmCard.poster_path" alt="">
        <div>{{cardTitle}}</div>
        <div>{{filteredName}}</div>
        <div>{{filmCard.original_language}}</div>
        <div>{{filmCard.vote_average}}</div>
            
    </div>

        
</template>

<script>
export default {
    name:'SingleCard',

    data:function(){
        return{
            imagePath:'poster_path',
            
            
        }
    },
    

    props:{
        filmCard:Object,
        
    },

    computed:{
        // funzione per filtrare i titoli di film  e serie tv
        cardTitle:function(){
            if(this.filmCard.title){
                return this.filmCard.title
            }else{
                return this.filmCard.name
            }
        },
        // end cardTitle

        // funzione per filtrare original_title e original_name

        filteredName:function(){

            if(this.filmCard.original_title){
                return this.filmCard.original_title
            }else{
                return this.filmCard.original_name
            }

        },

    },
    // end computed
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

.card{
    // test

    
    border:1px solid black;
    margin:20px;
    padding:20px;
    text-align: center;

        

}

</style>