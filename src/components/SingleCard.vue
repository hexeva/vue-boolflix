<template>
    <div class="card">
        <div>{{filmCard.title}}</div>
        <div>{{filmCard.original_title}}</div>
        <div>{{filmCard.original_language}}</div>
        <div>{{filmCard.vote_average}}</div>
            
    </div>

        
</template>

<script>
export default {
    name:'SingleCard',
    props:{
        filmCard:Object,
    }
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