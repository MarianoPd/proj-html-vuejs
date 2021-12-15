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
                <div v-for="(card, index) in plans" :key="index"
                    class="col-3 ">
                    <div class="my-card">
                        <h3>{{card.mainText}}</h3>
                        <div class="price">
                            <sup class="currency">$</sup>
                            <span class="integer-part">{{card.price}}</span>
                            <sup class="decimal-part">99</sup>
                            <span class="time">monthly</span>
                        </div>
                        <p>{{card.perks[0]}} Projects</p>
                        <p>{{card.perks[1]}} Storage</p>
                        <p>{{card.perks[2]}} Users</p>
                        <button class="my-btn" :class="index === 2 ? 'yellow' : 'white'">start today</button>
                    </div>
                </div>
          </div>
      </div>
  </div>
</template>

<script>

export default {
    name: 'Section4Plans',
    props:{
        plans: Array,
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
        
        .my-card{
            background-color: white;
            .price{
                position: relative;
                text-align: center;
                padding: 15px;
                .currency{
                    position: relative;
                    top: -20px;
                    font-size: 21px;
                    color: $primary-gray;
                }
                .integer-part{
                    display: inline;
                    font-size: 55px;
                    font-weight: 700;
                    color: $primary-blue;
                }
                .decimal-part{
                    position: relative;
                    top: -20px;
                    font-size: 17px;
                    font-weight: 700;
                    color: $primary-blue;
                }
                .time{
                    display: inline;
                    font-size: 11px;
                    font-weight: 700;
                    position: relative;
                    font-style: italic;
                    margin-left: -14px;
                }
            }
            h3{
                padding: 20px;
                color: $primary-blue;
            }
            p{
                color: $primary-gray;  
                display: block;  
                margin: 20px;
            }
            .my-btn{
                margin: 0 auto;
            }
            
        }
    }
}

</style>