<template>
  <Layout>
   <Hero :key="'hero'" />
   <Mission :key="'mission'" />
   <Services :key="'services'" />
   <Badges :key="'badges'" />
  </Layout>
</template>

<script>
import Hero from '~/components/Hero.vue'
import Mission from '~/components/Mission.vue'
import Services from '~/components/Services.vue'
import Badges from '~/components/Badges.vue'
export default {
  metaInfo: {
    title: 'Quality Managed Construction'
  },
  components: {
    Hero,
    Mission,
    Services,
    Badges
  }
}
</script>
