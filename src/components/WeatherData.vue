<template>
  <div class="p-4 md:p-10 border border-stone-800 bg-stone-900 rounded-lg h-[550px] md:h-[450px]">
    <div class="flex flex-col md:flex-row justify-between gap-4">
      <div>
        <h2 class="text-2xl md:text-3xl flex items-center gap-4">
          <i class="fa-solid fa-location-dot"></i> {{this.data.location.name}}
          <button 
            v-if="!myCitiesList.includes(this.data.location.name)"
            class="border border-emerald-300 flex md:hidden items-center gap-2 px-2 rounded-full overflow-hidden h-8 w-28 focus:bg-emerald-500 focus:text-white text-emerald-500 transition-all duration-300 ease-linear whitespace-nowrap text-lg"
            @click="handleNewCity"
          ><strong class="text-4xl ">+</strong> Add city</button>
        </h2>
        <div class="flex items-center justify-esnd mt-4 gap-2">
          <span>Lat: {{latitude}} º</span>
          <span>Long: {{longitude}} º</span>
        </div>
        <button 
          v-if="!myCitiesList.includes(this.data.location.name)"
          class="border border-emerald-300 text-emerald-400 mt-4 hidden md:flex items-center gap-2 px-2 rounded-full w-8 overflow-hidden h-8 hover:w-48 hover:bg-emerald-500 hover:text-white transition-all duration-300 ease-linear whitespace-nowrap"
          @click="handleNewCity"
        ><strong class="text-4xl ">+</strong> Add to your cities</button>
      </div>

      <div class="">
        <div class="flex justify-between">
          <p class="text-xl text-stone-300"><i class="fa-solid fa-calendar-days"></i> {{ getNameDay }}, {{this.data.forecast.items[this.currentWeather].date}}</p>
          <p class="text-lg text-stone-300"><i class="fa-solid fa-square-up-right"></i> Source: {{this.data.forecast.source}} </p>
        </div>

        <div class="flex flex-col md:flex-row gap-4">
          <div class="flex items-center justify-center md:justify-end mt-4 gap-8 md:gap-4 text-xl bg-gradient-to-bl from-stone-950 to-stone-800 p-4 rounded-lg">
            <span><strong class="text-5xl">{{this.data.forecast.items[this.currentWeather].temperature.max}}</strong> º max</span>
            <span><strong class="text-5xl">{{this.data.forecast.items[this.currentWeather].temperature.min}}</strong> º min</span>
          </div>

          <div class="flex items-center justify-center md:justify-end mt-4 gap-8 md:gap-4 text-xl bg-gradient-to-bl from-stone-950 to-stone-900 p-4 rounded-lg">
            <span><strong class="text-5xl">{{this.data.forecast.items[this.currentWeather].prec.probability}}</strong>% <i class="fa-solid fa-cloud-rain text-xl"></i></span>
            <span><strong class="text-5xl">{{this.data.forecast.items[this.currentWeather].wind.max}}</strong>km/h <i class="fa-solid fa-wind text-xl"></i></span>
          </div>
        </div>
      </div>
    </div>

    <ul class="mt-4 md:mt-10 py-4 flex gap-4 overflow-x-auto">
      <WeatherDay 
        v-for="(day, index) in this.data?.forecast.items"
        :key="index"
        :day="day"
        :isActive="this.currentWeather == index"
        @click="this.currentWeather = index"
      />
    </ul>
  </div>
</template>

<script>
import moment from 'moment'
import WeatherDay from './WeatherDay.vue';

export default {
  components: { WeatherDay },
    props: ['data', 'myCitiesList'],
    data() {
      return {
        day: 1,
        currentWeather: 0
      }
    },
    computed: {
      latitude(){
        const lat = String(this.data.location.coordinates.longitude).slice(0,4)
        return lat
      },
      longitude(){
        const long = String(this.data.location.coordinates.longitude).slice(0,5)
        return long
      },
      getNameDay() {
        return moment(this.data.forecast.items[this.currentWeather].date).format('dddd')
      },
    },  
    methods: {
      handleNewCity() {
        this.$emit('save-city', this.data.location.name)
      }
    }
}
</script>