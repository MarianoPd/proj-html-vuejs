<template>
  <div class="clients-carousel" >
    <div class="clients" >
      <div v-for="(item, index) in listToShow" :key="index"
        class="client" :class="{'active' : activeClient === index}">
        <div class="round-image">
          <img :src="require('@/assets/img/'+item.image)" :alt="item.image">
        </div>
        <p class="review">{{item.review}}</p>
        <p><strong>{{item.name}}</strong>, <span class="uppercase">{{item.position}}</span></p>
      </div>      
    </div>
    <div class="selectors">
      <div v-for="(number) in listToShow.length" :key="number"
        class="selector" @click="setThisClient(number - 1 )"
        :class="{'selected': activeClient === number -1}" ><a href="#"></a></div>
    </div>  
  </div>
</template>

<script>
export default {
    name: 'Carousel1',
    props:{
      listToShow: Array,
    },
    data(){
      return{
        activeClient: 0,
        interval: '',
      }
    },
    methods:{
      nextClient(){
        this.activeClient++;
        
        if(this.activeClient >= this.listToShow.length){
          this.activeClient = 0;
        }
        //console.log('nextClient',this.activeClient);
      },
      periodicNext(){
        this.interval = setInterval(() =>{
          //console.log('set interval');
          this.nextClient();
        }, 5000);
      },
      setThisClient(int){
        //console.log('set this',int);
        this.activeClient = int;
      }
    },
    
    mounted(){
      this.periodicNext();
    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.clients-carousel{
  width: 50%;
  padding-bottom: 40px;
  margin: 0 auto;
  .clients{
    .client{
      transition: opacity ease-in-out .5s;
      width: 50%;
      opacity: 0;
      z-index: -1;
      position: absolute;
      top: 0;
      left: 0;
      text-align: center;
      &.active{
        opacity: 1;
        z-index: 0;
        width: 100%;
        position: relative;
      }
      .round-image{
        width: 140px;
        aspect-ratio: 1;
        border-radius: 50%;
        overflow: hidden;
        margin: 0 auto;
        margin-bottom: 30px;
        img{ width: 100%;}
      }
      .review{
        font-size: 18px;
        font-style: italic;
      }
      .uppercase{
        text-transform: uppercase;
      }

    }
  }

  .selectors{
    text-align: center;
    .selector{
      display: inline-block;
      margin: 5px;
      width: 12px;
      aspect-ratio: 1;
      border: 1px solid black;
      border-radius: 50%;
      &.selected{
        background-color: black;
      }
    }
  }
}
</style>