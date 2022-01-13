<template>
        <div class="my_card">
            <!-- CARD IMAGE -->
            <div class="front_card ">
                <div class="image_found" >
                    <div class="not_found" v-if="filmCard.poster_path == null">
                        NO IMAGE FOUND
                        <div class="not_found_icon"><i class="far fa-frown fa-5x"></i></div>
                    </div>
                    <div class="image_box" v-else>
                        <img :src="`https://image.tmdb.org/t/p/w342/`+filmCard.poster_path" alt="">
                    </div>
                </div>
            </div>
            
            
            <!-- CARD INFO -->
               <div class="back_card">
                    <div>Title: {{cardTitle}}</div>
                    <div>Name: {{filteredName}}</div>
                    <div v-if="this.allLanguages.includes(filmCard.original_language)" class="flags">Lang: 
                        <img :src="require(`../assets/img/${filmCard.original_language}.png`)" alt="">
                    </div>
                    <div v-else>{{filmCard.original_language}}</div>
                    <div class="votes">Averages:
                        <i v-for="number in 5" :key="number" :class="{fas : number <= votes, far : number > votes}" class="fa-star"></i>
                    </div>
                    <div>Description: {{filmCard.overview}}</div>
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
            votes:parseInt(Math.ceil(this.filmCard.vote_average / 2)),
            
            
            
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

.my_card{
    border:1px solid $brand_background_color;
    background-color: $brand_background_color;
    border-radius:8px;
    margin:20px;
    padding:20px;
    text-align: center;
    cursor: pointer;

    .front_card{
        display: flex;
        flex-direction: column;
        height: 100%;
        justify-content: center;
        align-items: center;

    }

    
        .image_found{
            width:100%;
            height:100%;
            color: $brand_text_color;
            display: flex;
            justify-content: center;
            flex-direction: column;
            align-items: center;
           
            
               &>.image_box{
                   img{
                       max-width: 100%;
                   }
               }
        }
    .back_card{
        display: none;
        background-color: $brand_background_color;
        color: $brand_text_color;
        line-height: 21px;
        padding: 20px 0;
        text-align: start;
        height:100%;
        font-size: small;
    }
        

    .flags{
        img{
            width:20px;
        }
}

}


.my_card:hover .front_card{
    display:none;
}
.my_card:hover .back_card{
    display: block;
}
// end card


</style>