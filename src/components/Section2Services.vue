<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section2Services',
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-deep-cove;
    background-image: url('../assets/img/pattern_background.png');
    @include background-set();

    .my-subcontainer{
        height: 890px;
    }
}

</style>