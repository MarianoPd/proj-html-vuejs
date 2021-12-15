<template>
  <div class="container-fluid my-container">
        <div class="container my-subcontainer">
            <div class="my-head-text white">
                <h2>See Our Top Notch Services</h2>
                <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit assumenda fugit rem optio tenetur officiis sapiente maiores perferendis!</p>
            </div>
            <div class="row g-4">
            <div v-for="(card, index) in services" :key="index"
                class="col-3 ">
                <div class="my-card white">
                    <div class="card-top-text">
                        <i :class="card.iconClass"></i>
                        <h3>{{card.mainText}}</h3>
                    </div>
                    <p>{{card.bottomText}}</p>
                    <a href="#">Read More ></a>
                </div>
            </div>
        </div>
        </div>
        
  </div>
</template>

<script>

export default {
    name: 'Section2Services',
    props:{
        services: Array,
    },
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';
@import '@/assets/style/vars.scss';

.my-container{
    background-color: $bg-deep-cove;
    background-image: url('../assets/img/pattern_background.png');
    @include background-set();

    .my-subcontainer{
        
        .my-card{
            background-color: $secondary-lucky-point;             
            color: white;  
            a{
                color: $primary-yellow;
                text-decoration: none;
                font-size: 18px;
            }  
            
        }
    }
}

</style>