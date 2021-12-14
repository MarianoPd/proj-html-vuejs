<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <Carousel_1/>
      </div>
  </div>
</template>

<script>
import Carousel_1 from './Carousel_1.vue';
//import db from '@/assets/data/db.json'

export default {
    name: 'Section6Clients',
    components:{
        Carousel_1,
    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: white;
    
    .my-subcontainer{
        
    }
}

</style>