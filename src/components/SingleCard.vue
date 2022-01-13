<template>
        <div class="card">
            <!-- CARD IMAGE -->
            <div class="front_card">
                <div class="image_found" >
                    <div class="not_found" v-if="filmCard.poster_path == null">
                        NO IMAGE FOUND
                        <div><i class="far fa-frown fa-5x"></i></div>
                    </div>
                    <div class="image_box" v-else>
                        <img :src="`https://image.tmdb.org/t/p/w342/`+filmCard.poster_path" alt="">
                    </div>
                </div>
            </div>
            
            
            <!-- CARD INFO -->
               <div class="back_card d-none">
                    <div>{{cardTitle}}</div>
                    <div>{{filteredName}}</div>
                    <div v-if="this.allLanguages.includes(filmCard.original_language)" class="flags">
                        <img :src="require(`../assets/img/${filmCard.original_language}.png`)" alt="">
                    </div>
                    <div v-else>{{filmCard.original_language}}</div>
                    <div class="votes">
                        <i v-for="(star,index) in votes" :key="index" class="fas fa-star"></i>
                        <i v-for="(emptyStar,index) in (5 - votes)" :key="index" class="far fa-star"></i>
                    </div>
                    <div>{{filmCard.overview}}</div>
               </div>
            
        </div>
        <!-- END CARD -->

        
</template>

<script>
export default {
    name:'SingleCard',

    data:function(){
        return{
            imagePath:'poster_path',
            allLanguages:['it','fr','ja','en'],
            votes:parseInt(Math.round(this.filmCard.vote_average / 2)),
            
            
            
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
@import '../style/variables.scss';

@import '../style/general.scss';

.card{
    // test

    
    border:1px solid black;
    margin:20px;
    padding:20px;
    text-align: center;
    
        .image_found{
            width:100%;

               &>.image_box{
                   img{
                       max-width: 100%;
                   }
               }
        }
}
.flags{
    img{
        width:20px;
    }
}

</style>