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
                <div v-for="(card, index) in news" :key="index"
                    class="col-4 ">
                    <div class="my-card">
                        <div class="image-wrapper">
                            <img :src="require('@/assets/img/'+ card.image)" :alt="card.image">
                        </div>
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
export default {
    name: 'Section5News',
    props:{
        news: Array,
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
            .image-wrapper{
                width: 100%;
                aspect-ratio: 1.58;
                position: relative;
                overflow: hidden;
                img{
                                       
                    width: 100%;
                    margin-bottom: 10px;
                    &:hover{
                        transition: 0.5s;
                        width: 110%;
                        transform: translate(-5%); 
                    }
                }
            }
            img{
                width: 100%;
                margin-bottom: 10px;
                &:hover{

                }
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