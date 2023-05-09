<template>
  <div class="w-full md:w-3/5 mx-2 md:mx-auto bg-red-200 font-Raleway overflow-hidden">
    <NavBar />
    <router-view></router-view>
    <MainFooter />
  </div>
</template>

<script>
import MainFooter from './components/MainFooter.vue'
import NavBar from './components/NavBar.vue'

export default {
  components: { NavBar, MainFooter },

}
</script>
