<template>
  <div>
      <Section1Presentation :presentation = "cards.presentation"/>
      <Section2Services :services = "cards.services"/>
      <Section3Work :images= "images"/>
      <Section4Plans :plans= "cards.plans"/>
      <Section5News :news= "cards.news"/>
      <Section6Clients :clients= "cards.clients" :partners= "partners"/>
      <Section7Consultation/>

  </div>
</template>

<script>
import Section1Presentation from './Section1Presentation.vue';
import Section2Services from './Section2Services.vue';
import Section3Work from './Section3Work.vue';
import Section4Plans from './Section4Plans.vue';
import Section5News from './Section5News.vue';
import Section6Clients from './Section6Clients.vue';
import Section7Consultation from './Section7Consultation.vue';

export default {
    name: 'Main',
    components:{
        Section1Presentation,
        Section2Services,
        Section3Work,
        Section4Plans,
        Section5News,
        Section6Clients,
        Section7Consultation

    },
    props:{
        cards: Array,
        images:Array,
        partners: Array,
    }
}
</script>

<style scoped lang="scss">


</style>