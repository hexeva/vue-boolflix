<template>
    <div class="card">
        <ul>
            <li>{{filmCard.title}}</li>
            <li>{{filmCard.original_title}}</li>
            <li>{{filmCard.original_language}}</li>
            <li>{{filmCard.vote_average}}</li>

        </ul>
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

    width:300px;
    border:1px solid black;
    margin:20px;
    padding:20px;
    text-align: center;

        li{
            margin:5px 0;
        }

}

</style>