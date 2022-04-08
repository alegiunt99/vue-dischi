<template>
  <main class="container">
      <div v-if="songsGroup.length > 0" class="row">
          <SongCard  v-for="(item, index) in songsGroup" :key="index" :song="item" class="col col-md-6 col-lg-3"/>
      </div>
  </main>
</template>

<script>

import axios from 'axios';

import SongCard from '@/components/SongCard.vue';

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
    .row{
        margin: 89px 0px;
    }
</style>