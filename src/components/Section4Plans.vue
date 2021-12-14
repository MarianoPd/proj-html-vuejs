<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          <div class="my-head-text white">
              <h2>
                  Our Plans
              </h2>
              <p>
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit assumenda fugit rem optio tenetur officiis sapiente maiores perferendis!
              </p>
          </div>
          <div class="row">
                <div v-for="(card, index) in cardList" :key="index"
                    class="col-3 ">
                    <div class="my-card">
                        <i :class="card.iconClass"></i>
                        <h3>{{card.mainText}}</h3>
                        
                        <span>{{card.perks[0]}} Projects</span>
                        <span>{{card.perks[0]}} Storage</span>
                        <span>{{card.perks[0]}} Users</span>
                        
                    </div>
                </div>
          </div>
      </div>
  </div>
</template>

<script>
import db from '@/assets/data/db.json'
export default {
    name: 'Section4Plans',
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
        this.cardList = this.getList('plans');
    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-image: url('../assets/img/background1.jpg');;
    @include background-set();
    .my-subcontainer{
        height: 840px; //da togliere
        .my-card{
            background-color: white;
            h3{
                padding: 20px;
            }
            span{
                color: $primary-gray;  
                display: block;  
                margin-bottom: 40px;
            }
            
        }
    }
}

</style>