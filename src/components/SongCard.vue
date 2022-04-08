<template>
    <div class="card-song">

        <img :src="song.poster">

        <h4 id="song-title">{{song.title}}</h4>

        <p>{{song.author}}</p>

        <span>{{song.year}}</span>

    </div>
</template>

<script>
export default {

    name: 'SongCard',

    props:{
        song: Object
    }

}
</script>

<style lang="scss" scoped>

    .card-song{
        padding: 19px;
        text-align: center;
        background-color: #2e3a46;
        border: 11px solid #1e2d3b;
        img{
            width: 85%;
        }
        h4{
            color: white;
            margin-top: 20px;
            text-transform: uppercase;
        }
        p,
        span{
            color: gray;
            font-size: 16px;
        }

        p{
            margin-bottom: 0;
            margin-top: 22px;
        }
    }

</style>