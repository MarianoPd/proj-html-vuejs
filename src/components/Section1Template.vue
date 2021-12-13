<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          <div class="top-content">
              top
          </div>
          <div class="bottom-content d-flex justify-content-center">
              <img src="@/assets/img/agency-seo-desk-front.jpg" alt="agency-seo-desk">
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section1Template',
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-alabaster;
    
    .my-subcontainer{
        height: 1350px;  //da rimuovere
        .top-content{
            height: 50%; //da rimuovere
        }
        .bottom-content{
            height: 50%; //da rimuovere
        }
    }
}

</style>