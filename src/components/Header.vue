<template>
    <div class="container">
        <div class="search_bar">
            <input class="form-control" v-model="searchMovie" id="Search" type="text" placeholder="Cerca un film">
            <button class="btn btn-primary"  @click="$emit('research',searchMovie)">Invia ricerca</button>
        </div>
        
    </div>
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

    .search_bar{
    display: flex;
}



</style>