<template>
  <div class="container-fluid my-container p-0">
      <div class=" my-subcontainer p-0 m-0 w-100">
          <div class="center-piece">
              <div class="my-head-text white">
                <h2>
                    Start Your Free Consultation
                </h2>
                <p>
                    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit assumenda fugit rem optio tenetur officiis sapiente maiores perferendis!
                </p>
            </div>
            <div class="my-btn-container">
                    <button class="my-btn yellow">go to news</button>
            </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section7Consultation',
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-image: url('../assets/img/CTA-seo-1.jpg');
    background-position: center;
    .my-subcontainer{
        @include center();
        background-color: rgba(0,0,0,.4);
        color: white;
        .center-piece{
            padding: 100px 0;
            .my-head-text{
                margin-bottom: 30px;
            }
            .my-btn-container{
                width: 100%;
                @include center();
                
                padding-bottom: 10px;
            }
        }
        
    }
    
}


</style>