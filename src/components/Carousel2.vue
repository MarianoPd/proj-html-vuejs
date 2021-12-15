<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            <transition name="slide-left">
                <div class="slider-wrapper clearfix">
                <div :style="{ left: sliding}" 
                    class="slider-holder clearfix">
                    <div v-for="(item,index) in imgToShow" :key="index"
                        class="slider-item">
                        <img :src="require('../assets/img/' + item.name)" 
                            alt="item.name">
                    </div>                    
                </div>
            </div>
            </transition>  
      </div>
  </div>
</template>

<script>
export default {
    name: 'Carousel2',
    props:{
      imgToShow: Array,
    },
    data(){
      return{
        sliding: '0',
        interval: '',
      }
    },
    methods:{
        slide(){
            this.sliding ='-50%';
            //non servono ma mi piacce di piu'
            let element = this.imgToShow.shift(); 
            this.imgToShow.push(element);
        },
        keepSliding(){
            this.interval = setInterval(() =>{
            //console.log('set interval');
            this.slide();
        }, 5000);
        },

        //tentativo di transition fai-da-te fallito
        easySlide(){
            if(this.sliding === '0') return;
            let numb = parseInt(this.sliding);
            for(let i= 0; i< 10; i++){
                setTimeout(() =>{
                    numb += 5;
                    this.sliding = numb.toString();
                } ,100);
            }
        }
    },
    mounted(){
        this.keepSliding();
    }

}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-subcontainer{
    padding-top: 0  ;
    padding-bottom: 0  ;
    /*.slide-left-enter-active {
        transition: all .8s ease;
    }  
    .slide-fade-leave-active{
        transition: all .8s ease;
    }    */ 
    .slider-wrapper{
        border-top: 1px solid lighten($secondry-gray-light, 30%);
        padding: 50px 0 40px 0;        
        position: relative;
        overflow: hidden;
        height: 190px;
        .slider-holder{
            position: absolute;
            width: 150%;
            height: 100%;
            
            .slider-item{
                width: calc(100% /6);
                float: left;
                text-align: center;
                img{
                    height: 100px;
                    margin: auto;
                }
            }
        }
    }
}
//le transition non funzionano
/*.slide-fade-enter-active {
  transition: left .8s ease;
}
.slide-fade-leave-active{
        transition: left .8s ease;
} */

</style>