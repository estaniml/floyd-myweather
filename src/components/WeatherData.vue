<template>
  <div class="p-4 md:p-10 border border-stone-800 bg-stone-900 rounded-lg h-[550px] md:h-[450px]">
    <div class="flex flex-col md:flex-row justify-between gap-4">
      <div>
        <h2 class="text-2xl md:text-4xl flex items-center gap-4">
          <i class="fa-solid fa-location-dot"></i> {{this.data.location.name}}
          <button 
            class="border border-emerald-300 flex md:hidden items-center gap-2 px-2 rounded-full overflow-hidden h-8 w-28 focus:bg-emerald-500 focus:text-white text-emerald-500 transition-all duration-300 ease-linear whitespace-nowrap text-lg"
            @click="handleNewCity"
          ><strong class="text-4xl ">+</strong> Add city</button>
        </h2>
        <div class="flex items-center justify-esnd mt-4 gap-2">
          <span>Lat: {{this.data.location.coordinates.latitude}} º</span>
          <span>Long: {{this.data.location.coordinates.longitude}} º</span>
        </div>
        <button 
          class="border border-emerald-300 text-emerald-400 mt-4 hidden md:flex items-center gap-2 px-2 rounded-full w-8 overflow-hidden h-8 hover:w-48 hover:bg-emerald-500 hover:text-white transition-all duration-300 ease-linear whitespace-nowrap"
        ><strong class="text-4xl ">+</strong> Add to your cities</button>
      </div>

      <div class="">
        <div class="flex justify-between">
          <p class="text-xl text-stone-300"><i class="fa-solid fa-calendar-days"></i> Date: {{this.data.forecast.forecastDate.slice(0,9)}}</p>
          <p class="text-lg text-stone-300"><i class="fa-solid fa-square-up-right"></i> Source: {{this.data.forecast.source}} </p>
        </div>

        <div class="flex flex-col md:flex-row gap-4">
          <div class="flex items-center justify-center md:justify-end mt-4 gap-8 md:gap-4 text-xl bg-gradient-to-bl from-stone-950 to-stone-800 p-4 rounded-lg">
            <span><strong class="text-6xl">{{this.data.forecast.items[0].temperature.max}}</strong> º max</span>
            <span><strong class="text-6xl">{{this.data.forecast.items[0].temperature.min}}</strong> º min</span>
          </div>

          <div class="flex items-center justify-center md:justify-end mt-4 gap-8 md:gap-4 text-xl bg-gradient-to-bl from-stone-950 to-stone-900 p-4 rounded-lg">
            <span><strong class="text-6xl">{{this.data.forecast.items[0].prec.probability}}</strong>% <i class="fa-solid fa-cloud-rain text-xl"></i></span>
            <span><strong class="text-6xl">{{this.data.forecast.items[0].wind.max}}</strong>km/h <i class="fa-solid fa-wind text-xl"></i></span>
          </div>
        </div>
      </div>
    </div>

    <ul class="mt-4 md:mt-10 py-4 flex gap-4 overflow-x-auto">
      <WeatherDay 
        :key="index"
        v-for="(day, index) in this.data?.forecast.items.slice(1)"
        :day="day"
      />
    </ul>
  </div>
</template>

<script>
import WeatherDay from './WeatherDay.vue';
export default {
  components: { WeatherDay },
    props: ['data'],
    data() {
      return {
        day: 1
      }
    },
    mounted() {
      console.log(this.data);
    },
    methods: {
      handleNewCity() {
        this.$emit('show-weather', this.data.location.name)
      }
    }
}
</script>

<style>

</style>