<template>
  <div class="container-fluid my-container">
    <div class="container my-subcontainer">
      <div class="top-header"></div>
      <div class="center-header"></div>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '@/assets/style/mixins.scss';

.my-container{
  background-image: url('../assets/img/1-hero-image.png');
  @include background-set();

  .my-subcontainer{
    height: 865px; //da togliere
    .top-header{

    }
    .center-header{
      
    }
  }
}


</style>
