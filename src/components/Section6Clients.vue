<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <div class="my-head-text">
                <h2>
                    What Our Clients Say
                </h2>
            </div> 
            
            <Carousel1 :listToShow="cardList" />
            <Carousel2 :imgToShow="partnerList" />
      </div>
  </div>
</template>

<script>
import Carousel1 from './Carousel1.vue';
import Carousel2 from './Carousel2.vue';
import db from '@/assets/data/db.json'

export default {
    name: 'Section6Clients',
    components:{
        Carousel1,
        Carousel2,
    },
    data(){
        return{
            cardList: [],
            partnerList: [],
        }
    },
    methods:{
        getCardList(type){
            let array = db.cards.filter( card => card.type == type);
            return array;
        },
        getPartnerList(){
            let array = db.partners;
            return array;
        }
    },
    mounted(){
        this.cardList = this.getCardList('clients');
        this.partnerList = this.getPartnerList();
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