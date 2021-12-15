<template>
  <div id="app">
    <Header :links = "linkList"/>
    <Main :cards = "cardList" :images= "imageList" :partners= "partnersList"/>
    <Footer :links = "linkList"/>
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'
import db from './assets/data/db.json'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
  data(){
    return{
      linkList: db.links,
      cardList: db.cards,
      imageList: db.images,
      partnersList: db.partners,
    }
  },
  methods:{
    
  },
  mounted(){
    //console.log(this.linkList);
  },
}
</script>

<style lang="scss">
@import './assets/style/vars.scss';
@import './assets/style/generals.scss';
@import './assets/style/mixins.scss';
@import './assets/style/utilities.scss';

#app {
  
}
</style>
