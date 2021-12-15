<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <div class="my-head-text">
                <h2>Our Work</h2>
                <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.</p>
            </div>
            <div class="row g-3">
                <div v-for="(image,index) in images"  :key="index"  class="col-4">
                    <div  class="image-cont">
                        <img :src="require('@/assets/img/'+ image.name)" :alt="image.name">
                        <div class="hover-effect"><i class="fas fa-link"></i></div>
                    </div>
                </div>
                
            </div>
            <div class="my-btn-container">
                <button class="my-btn yellow">view our work</button>
            </div>          
      </div>
  </div>
</template>

<script>
export default {
    name: 'Section3Work',
    props:{
        images: Array,
    }
    
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-alabaster;
    
    .my-subcontainer{
        
        .image-cont{
            position: relative;
            img{
                width: 100%
            };
            .hover-effect{
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                @include center();
                z-index: 99;
                font-size: 35px;
                color: white;
                background: linear-gradient($primary-blue, $primary-blue-transparent) ;
                opacity: 0;
                &:hover{
                    transition: opacity 0.5s;
                    opacity: 1;
                }
            }
            
        }
        .my-btn-container{
            width: 100%;
            @include center();
            padding-top: 75px;
        }
    }
}

</style>