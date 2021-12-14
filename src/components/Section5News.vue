<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          <div class="my-head-text ">
              <h2>
                  Our News
              </h2>
              <p>
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit assumenda fugit rem optio tenetur officiis sapiente maiores perferendis!
              </p>
          </div>
          <div class="row">
                <div v-for="(card, index) in cardList" :key="index"
                    class="col-4 ">
                    <div class="my-card">
                        <img :src="require('@/assets/img/'+ card.image)" :alt="card.image">
                        <h3>{{card.mainText}}</h3>
                        <span>{{card.date}}</span>
                        <p>{{card.bottomText}}</p>
                        
                    </div>
                </div>
          </div>
          <div class="my-btn-container">
                <button class="my-btn yellow">go to news</button>
          </div>
      </div>
  </div>
</template>

<script>
import db from '@/assets/data/db.json'
export default {
    name: 'Section5News',
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
        this.cardList = this.getList('news');
    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-alabaster;
    
    .my-subcontainer{
        
        .my-card{
            padding: 0;
            img{
                width: 100%;
                margin-bottom: 10px;
            }
            h3{
                color: $primary-yellow;
                padding: 0;
            }
            span{
                color: $primary-gray
            }
            p{
                color: $primary-gray;
                margin-top: 15px;
            }
        }

        .my-btn-container{
            width: 100%;
            @include center();
            padding-top: 35px;
            padding-bottom: 10px;
        }
    }
}

</style>