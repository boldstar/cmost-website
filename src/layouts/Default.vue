<template>
  <div class="layout">
    <Navbar />
    <main>
      <transition-group name="fade" appear>
        <slot/>
      </transition-group>
    </main>
    <Contact />
    <Footer />
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<script>
import Navbar from '~/components/Navbar.vue'
import Contact from '~/components/Contact.vue'
import Footer from '~/components/Footer.vue'
export default {
  name: 'Default',
  components: {
    Navbar,
    Contact,
    Footer
  }
}
</script>


<style src="~/css/main.css" />

