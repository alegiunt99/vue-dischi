<template>
  <div id="app">
    <SpotyHeader />
    <SongsContainer />
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
  }
}
</script>

<style lang="scss">

@import '@/style/style';

</style>
