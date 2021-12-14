<template>
  <div>
      <Section1Template/>
      <Section2Services/>
      <Section3Work/>
      <Section4Plans/>
      <Section5News/>
      <Section6Clients/>
      <Section7Consultation/>

  </div>
</template>

<script>
import Section1Template from './Section1Template.vue';
import Section2Services from './Section2Services.vue';
import Section3Work from './Section3Work.vue';
import Section4Plans from './Section4Plans.vue';
import Section5News from './Section5News.vue';
import Section6Clients from './Section6Clients.vue';
import Section7Consultation from './Section7Consultation.vue';

export default {
    name: 'Main',
    components:{
        Section1Template,
        Section2Services,
        Section3Work,
        Section4Plans,
        Section5News,
        Section6Clients,
        Section7Consultation

    }
}
</script>

<style scoped lang="scss">
@import '@/assets/style/mixins.scss';

</style>