<template>
  <div class="w-full lg:w-4/5 xl:w-3/5 px-2 lg:mx-auto font-Raleway overflow-hidden">
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
