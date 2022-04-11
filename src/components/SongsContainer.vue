<template>
  <main class="container">
      <!-- aggiungo una select con i generi di musica -->
    <div class="row" id="songs-genre">
        <MusicType @genre="filterByGenre" class="col-1"/>
    </div>

    <!-- creo le card delle canzoni  -->
    <div v-if="songsGroup.length > 0" class="row" id="songs-container">
          <SongCard  v-for="(item, index) in filteredList" :key="index" :song="item" class="col col-md-6 col-lg-3"/>
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

            genreSelected: ''
        }

    },

    props: {
        songs: String
    },

    components:{
        SongCard,
        MusicType
    },

    computed:{

        filteredList(){

            if(this.genreSelected.length === 0){

                return this.songsGroup;

            } else (this.genreSelected.length > 0);{

                return this.songsGroup.filter( (item) => {

                item.genre.toLowerCase().includes(this.genreSelected.toLowerCase());
    
            })

            }

            
            
        },


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

                        //console.log(this.songsGroup);

                    }
                }
            )
        },

        
        filterByGenre(genre){

            this.genreSelected = genre

            console.log('il GENERE SELEZIONATO è', this.genreSelected);

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