<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <div class="my-head-text">
                <h2>Our Work</h2>
                <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.</p>
            </div>
            <div class="row g-3">
                <div  class="col-4">
                    <div class="image-cont">
                        <img src="../assets/img/case-study-gallery-3-1.jpg" alt="case-study-gallery-3-1">
                    </div>
                </div>
                <div  class="col-4">
                    <div class="image-cont">
                        <img src="../assets/img/case-study-gallery-2.jpg" alt="case-study-gallery-2">
                    </div>
                </div>
                <div  class="col-4">
                    <div class="image-cont">
                        <img src="../assets/img/case-study-gallery-1-1.jpg" alt="case-study-gallery-1-1">
                    </div>
                </div>
                <div  class="col-4">
                    <div class="image-cont">
                        <img src="../assets/img/case-study-gallery-4-1.jpg" alt="case-study-gallery-4-1">
                    </div>
                </div>
                <div  class="col-4">
                    <div class="image-cont">
                        <img src="@/assets/img/case-study-gallery-5-1.jpg" alt="case-study-gallery-6-1">
                    </div>
                </div>
                <div  class="col-4">
                    <div class="image-cont">
                        <img src="@/assets/img/case-study-gallery-6-1.jpg" alt="case-study-gallery-6-1">
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
import db from '../assets/data/db.json'
export default {
    name: 'Section3Work',
    data(){
        return{
            imageList: [],  //non usato perché Vue è infame
        }
    },
    methods:{
        
    },
    mounted(){
        this.imageList = db.images;
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