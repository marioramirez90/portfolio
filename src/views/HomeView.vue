<template>
  <div id="Home">
    <header><HomeViewNavbar /></header>
    <div class="about"><AboutMe /></div>
    <HomeViewMySkills />
    <HomeViewProject />
    <HomeViewContact />
    <HomeViewFooter />
  </div>
</template>

<script>
import HomeViewNavbar from '/src/components/HomeViewNavbar.vue'
import AboutMe from '@/components/AboutMe.vue'
import HomeViewProject from '@/components/HomeViewProject.vue'
import HomeViewMySkills from '@/components/HomeViewMySkills.vue'
import HomeViewContact from '@/components/HomeViewContact.vue'
import HomeViewFooter from '@/components/HomeViewFooter.vue'

export default {
  components: {
    HomeViewNavbar,
    AboutMe,
    HomeViewProject,
    HomeViewMySkills,
    HomeViewContact,
    HomeViewFooter
  }
}
</script>

<style scoped>
header {
  position: fixed;
  width: 100%;
  z-index: 1000;
}
</style>
