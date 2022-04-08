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
        color: white;
        img{
            width: 85%;
        }
    }

</style>