<template>
    <div>
        <input v-model="searchMovie" id="Search" type="text" placeholder="Cerca un film">
        <button  @click="$emit('research',searchMovie)">Invia ricerca</button>
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

</style>