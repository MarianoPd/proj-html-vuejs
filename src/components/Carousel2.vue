<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer">
            
                <div class="slider-wrapper clearfix">
                <div :class="{'slided': sliding}" 
                    class="slider-holder clearfix">
                    <div v-for="(item,index) in imgToShow" :key="index"
                        class="slider-item">
                        <img :src="require('../assets/img/' + item.name)" 
                            alt="item.name">
                    </div>                    
                </div>
            </div>
              
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
        sliding: false,
        interval: '',
      }
    },
    methods:{
        slide(){
            this.sliding = true;
            //non servono ma mi piacce di piu'
            setTimeout(()=>{
                let element = this.imgToShow.shift(); 
                this.imgToShow.push(element);
                this.sliding = false;
            },1000);
        },
        keepSliding(){
            this.interval = setInterval(() =>{
            //console.log('set interval');
            this.slide();
            
        }, 5000);
        },
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
    
    .slider-wrapper{
        border-top: 1px solid lighten($secondry-gray-light, 30%);
        padding: 50px 0 40px 0;        
        position: relative;
        overflow: hidden;
        height: 190px;
        
        .slider-holder{
            position: absolute;
            left: 0;
            width: 150%;
            height: 100%;
            &.slided{ 
                left: -25%;
                transition: left ease 1.0s;
            }

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

</style>