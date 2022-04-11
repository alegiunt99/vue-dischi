<template>
  <main class="container">
      <div class="row" id="songs-genre">
        <select name="songs-type" class="col-1" >
            <option value="">All</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
        </select>
      </div>
      
      <div v-if="songsGroup.length > 0" class="row" id="songs-container">
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
    #songs-container{
        margin: 89px 0px;
    }


    #songs-genre{
        justify-content: center;
        select{
            padding: 7px;
            border-radius: 10px;
            color: white;
            background-color: #2e3a46;
            margin-top: 35px;
            border: none;
            font-size: 17px;
        }
    }
</style>