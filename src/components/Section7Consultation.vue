<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section7Consultation',
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    position: relative;
    
    .my-subcontainer{
        position: relative;
        height: 480px; //da togliere
    }
    &::before{
        content: "";
        position: absolute;
        top: 0; left: 0;
        width: 100%; height: 100%;
        background-image: url('../assets/img/CTA-seo-1.jpg');
        filter: brightness(40%);
        @include background-set();
    }
}


</style>