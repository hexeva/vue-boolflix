<template>
    <header>
        <div class="container">
            <div class="header_bar">
                <div class="logo">
                    <img src="../assets/img/netflixlogo.png" alt="logo netflix">
                </div>
                <div class="search_bar">
                    <input class="form-control" v-model="searchMovie" id="Search" type="text" placeholder="Cerca un film">
                    <button class="btn btn-primary btn-sm"  @click="$emit('research',searchMovie)">Ricerca un film</button>
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

header{
        height:80px;

            .search_bar{
        display: flex;
        height: 30px;
    }
        .logo{
            width:60px;
    }

    
}





</style>