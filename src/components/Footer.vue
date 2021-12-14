<template>
  <div class="container-fluid my-container">
      <div class="container my-subcontainer ">
          <div class="image">
              <img src="../assets/img/logo_seo_1x.png" alt="logo_seo_w_1x">
          </div>
          <div class="menu-footer d-flex justify-content-between align-items-center">            
            <ul>
            <li v-for="(link,index) in links" :key="index">
                <a v-if="link.id === 1" class="text-yellow"  :href="link.link">{{link.name}}</a>
                <a v-else :href="link.link">{{link.name}}</a>
            </li>
            </ul>
        </div>
        <div class="credits">
            <p>
                &copy; Copyright 2012 - 2020 | Avada Theme by <a href="#">Theme Fusion</a>
                 | All Rights Reserved | Powered by <a href="#">WordPress</a>
            </p>
        </div>
        <div class="socials">
            <a href="#"><i class="fab fa-facebook-f"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-youtube"></i></a>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Footer',
    props: {
        links: Array,
    },
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-alabaster;
    
    .my-subcontainer{
        height: 325px; //da togliere
        padding: 45px 0;
        .image{
            margin: 0 auto;
            display: block;
            @include center();
        }
        .menu-footer{
            height: 130px;
            & > *{
                margin: 0 auto;
            }
            ul{                
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
        .credits{
            color: $secondry-gray-light;
            text-align: center;
            a{
                color: $primary-gray;
                text-decoration: none;
                &:hover{
                    color: $primary-yellow
                }
            }   
        }
        .socials{
            text-align: center;
            a{
                margin:0 10px ;
                color: $primary-gray;
                font-size: 20px;
            }
        }
    }
}
</style>