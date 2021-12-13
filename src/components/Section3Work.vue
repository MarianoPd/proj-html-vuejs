<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section3Work',
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-alabaster;
    
    .my-subcontainer{
        height: 1120px; //da togliere
    }
}

</style>