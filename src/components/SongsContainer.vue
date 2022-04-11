<template>
  <main class="container">
      <!-- aggiungo una select con i generi di musica -->
    <div class="row" id="songs-genre">
        <MusicType />
    </div>

    <!-- creo le card delle canzoni  -->
    <div v-if="songsGroup.length > 0" class="row" id="songs-container">
          <SongCard  v-for="(item, index) in songsGroup" :key="index" :song="item" class="col col-md-6 col-lg-3"/>
    </div>
  </main>
</template>

<script>

import axios from 'axios';

import SongCard from '@/components/SongCard.vue';

import MusicType from '@/components/MusicType.vue'

export default {

    name: 'SongsContainer',

    data(){

        return {
            songsGroup: [],
        }

    },

    props: {
        songs: String
    },

    components:{
        MusicType, 
        SongCard
    },

    mounted(){
        this.loadData();
    },

    methods: {
        loadData(){
            axios.get(this.songs).then( 
                (risultato) => {

                    if(risultato.status === 200){

                        this.songsGroup = risultato.data.response;

                        console.log(this.songsGroup);

                    }
                }
            )
        }
    }

}
</script>

<style lang="scss" scoped>
    #songs-container{
        margin: 89px 0px;
    }


    #songs-genre{
        justify-content: center;
    }
</style>