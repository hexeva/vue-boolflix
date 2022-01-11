<template>
    <div>
        <input id="Search" type="text" placeholder="Cerca">
        <button @click="callApi">Invia ricerca</button>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name:'Header',

    methods:{

        callApi: function(){
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params:{
                    api_key:'3b8e65acb65bbd04677cf76f0c18bc6d',
                    query:'terminator'
                }
            })
            .then((response) => {
                console.log(response.data.results);
            });
        }
        
        
    },
}


</script>

<style lang="scss" scoped>

</style>