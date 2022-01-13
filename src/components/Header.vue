<template>
    <header>
        <div class="my_container">
            <div class="header_bar">
                <div class="logo">
                    <img src="../assets/img/netflixlogo.png" alt="logo netflix">
                </div>
                <div class="search_bar">
                    <input class="form-control mx-4" v-model="searchMovie" id="Search" type="text" placeholder="Cerca un film">
                    <button class="btn rounded"  @click="$emit('research',searchMovie)">Search</button>
                </div>
            </div>
        </div>
      
       
    </header>
</template>

<script>
// import axios from 'axios';
export default {
    name:'Header',

    data:function(){
        return{
            searchMovie:'',
        };

    },

    methods:{

    },
}


</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
@import '../style/general.scss';


header{
    background-color:$brand_background_color;
        height:80px;
        .header_bar{
            display:flex;
            justify-content: space-between;
            align-items: center;
            line-height: 80px;
        }

            .search_bar{
                 height: 35px;
                 display: flex;
                 justify-content: space-between;

                 button{
                     background-color:$brand_logo_color;
                     color:white;
                 }
    }
        .logo{
            width:80px;
    }

    
}





</style>