<template>
  <div class="container-fluid my-container">
    <div class="container my-subcontainer">
      <div class="top-header d-flex justify-content-between align-items-center">
        <img src="../assets/img/logo_seo_w_1x.png" alt="logo_seo_w_1x">
        <ul>
          <li v-for="(link,index) in links" :key="index">
            <button v-if="link.id === links.length" class="my-btn mini yellow">{{link.name}}</button>
            <a v-else-if="link.id === 1" class="text-yellow"  :href="link.link">{{link.name}}</a>
            <a v-else :href="link.link">{{link.name}}</a>
          </li>
        </ul>
      </div>
      <div class="center-header ">
        <div>
          <h1>SEM Campaigns Made Simple With Avada</h1>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Incidunt laudantium tenetur iste labore id. Doloribus!</p>
          <div class="d-flex">
            <button class="my-btn yellow">buy avada now</button>
            <button class="my-btn blue ">contact us</button>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    links: Array,
  },
  mounted(){
    //console.log(this.links);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
  background-image: url('../assets/img/1-hero-image.png');
  @include background-set();
  overflow-x: hidden; 
  .my-subcontainer{
    height: 100vh; 
    padding: 0;
    .top-header{
      height: 90px;
      ul{
        color: white;
        display: flex;
        flex-direction: row;
        justify-content: center;
        
        li{
          padding-right: 35px;
          a{
            text-decoration: none;
          }
          a:hover{
            color: $primary-yellow;
          }
          .text-yellow{
            color: $primary-yellow;
          }
        }
      }
    }
    .center-header{
      padding-right: 50%;
      padding-top: 150px;
      color: white;
      
      h1{
        font-size: 54px;
        font-weight: 700;
      }
      p{
        font-size: 21px;
        padding: 20px 0;
      }
      .my-btn{
        margin-right: 20px;
      }
    }
  }
}


</style>
