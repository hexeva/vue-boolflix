<template>
    <div class="card">
        <ul>
            <li>{{filmCard.title}}</li>
            <li>Titolo originale</li>
            <li>Lingua</li>
            <li>Voto</li>

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

    width:100px;
    border:1px solid black;
    margin:20px;
    padding:20px;
    text-align: center;

        li{
            margin:5px 0;
        }

}

</style>