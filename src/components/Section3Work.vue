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
            img{
                width: 100%
            };
        }
        .my-btn-container{
            width: 100%;
            @include center();
            padding-top: 75px;
        }
    }
}

</style>