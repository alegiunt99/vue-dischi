<template>
  <div id="app">
    <SpotyHeader />
    <SongsContainer :songs='urlSongs'/>
  </div>
</template>

<script>
import SpotyHeader from '@/components/SpotyHeader.vue';

import SongsContainer from '@/components/SongsContainer.vue'

export default {
  name: 'App',
  components: {
   
    SpotyHeader,

    SongsContainer
  },

  data(){

    return {

      urlSongs: 'https://flynn.boolean.careers/exercises/api/array/music',
    
    }

  }
}
</script>

<style lang="scss">

@import '@/style/style';

</style>
