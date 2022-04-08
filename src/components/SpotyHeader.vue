<template>
  <header class="container-fluid">
      <div class="row">
          <div class="col-2">
              <img src="@/assets/spotify-logo.png" alt="">
          </div>
      </div>

  </header>
</template>

<script>


export default {
    name: 'SpotyHeader',
}
</script>

<style lang="scss" scoped>

    @import '@/style/variables';

    header{
        background-color: $header-color;
        .col-2{
            padding: 20px 5px;
            img{
                width: 35%;
            }
        }
    }
    

</style>