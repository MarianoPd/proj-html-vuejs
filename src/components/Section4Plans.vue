<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section4Plans',
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-image: url('../assets/img/background1.jpg');;
    @include background-set();
    .my-subcontainer{
        height: 900px; //da togliere
    }
}

</style>