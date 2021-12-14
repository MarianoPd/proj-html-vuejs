<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <div class="my-head-text">
                <h2>
                    What Our Clients Say
                </h2>
            </div> 
            
            <Carousel1 :listToShow="cardList" />
      </div>
  </div>
</template>

<script>
import Carousel1 from './Carousel1.vue';
import db from '@/assets/data/db.json'

export default {
    name: 'Section6Clients',
    components:{
        Carousel1,
    },
    data(){
        return{
            cardList: [],
        }
    },
    methods:{
        getList(type){
            let array = db.cards.filter( card => card.type == type);
            return array;
        }
    },
    mounted(){
        this.cardList = this.getList('clients');
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