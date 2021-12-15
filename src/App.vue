<template>
  <div id="app">
    <Header :links = "linkList"/>
    <Main/>
    <Footer :links = "linkList"/>
    <button class="up-btn"><a href="#"><i class="fas fa-chevron-up"></i></a></button>
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
  scroll-behavior: smooth;
  .up-btn{
    position: fixed;
    bottom: 0;
    right: 70px;
    background-color: $primary-gray;
    width: 45px;
    height: 35px;
    border-radius: 7px 7px 0 0;
    border: 0;
    a{
      color: white;
      text-decoration: none;
    }
    &:hover{
      transition: 0.2s;
      background-color: $primary-yellow;
    }
  }
  
}
</style>
