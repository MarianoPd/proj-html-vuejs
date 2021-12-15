<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
          <div class="top-content">
                <div class="my-head-text">
                    <h2>Meet The New Agency SEO Template From The Avada Team</h2>
                    <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.</p>
                </div>
                <div class="row g-4 ">
                    <div v-for="(card, index) in presentation" :key="index"
                        class="col-12 col-xl-4 ">
                        <div class="my-card">
                            <div class="card-top-text">
                                <i :class="card.iconClass"></i>
                                <h3>{{card.mainText}}</h3>
                            </div>
                            <p>{{card.bottomText}}</p>
                        </div>
                    </div>
                </div>
          </div>
          <div class="bottom-content d-flex justify-content-center">
              <img src="@/assets/img/agency-seo-desk-front.jpg" alt="agency-seo-desk">
          </div>
      </div>
  </div>
</template>

<script>

export default {
    name: 'Section1Presentation',
    props:{
        presentation: Array,
    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';


.my-container{
    background-color: $bg-alabaster;
    
    .my-subcontainer{
        
        padding-bottom: 0;
        .top-content{
            .my-card{
                background-color: white;  
                      
                p{
                    color: $primary-gray;                    
                }
            }
            
        }
        .bottom-content{
            
            img{
                max-width: 100%;
            }
        }
    }
}

</style>