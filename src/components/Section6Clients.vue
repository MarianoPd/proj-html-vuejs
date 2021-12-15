<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <div class="my-head-text">
                <h2>
                    What Our Clients Say
                </h2>
            </div> 
            
            <Carousel1 :listToShow= "clients" />
            <Carousel2 :imgToShow= "partners" />
      </div>
  </div>
</template>

<script>
import Carousel1 from './Carousel1.vue';
import Carousel2 from './Carousel2.vue';

export default {
    name: 'Section6Clients',
    components:{
        Carousel1,
        Carousel2,
    },
    props:{
        clients: Array,
        partners: Array,
    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: white;
    
    .my-subcontainer{
        padding-bottom: 0;
    }
}

</style>