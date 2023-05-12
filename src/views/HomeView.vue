<template>
  <main class="pt-4 md:pt-10 bg-black min-h-screen">
    <h2 class="mb-4 text-2xl text-emerald-500 font-bold">★ Your cities</h2>
    <MyCities 
      @show-weather="showCityWeather"
      @remove-city="removeCity"
      :myCitiesList="this.myCities"
    />

    <h2 class="mb-4 text-2xl text-emerald-500 font-bold">☀ Search a new city</h2>
    <div class="flex items-center gap-2 h-full mb-8">
      <input 
        type="text"
        v-model="search"
        class="bg-black w-full border border-stone-500 rounded-lg p-2 focus:outline-none focus:border-emerald-500 text-sm"
        placeholder="Type here the city..."
        ref="searchInput"
      />
      <button
        class="bg-white text-black hover:opacity-50 text-sm p-2 rounded-lg font-medium"
        @click="searchWeather"
      >Search</button>
    </div>

    <WeatherData 
      :data="data"
      @save-city="saveNewCity"
      :myCitiesList="this.myCities"
      v-if="data"
    />

    <WeatherDataLoader 
      v-else-if="loading"
    />

    <ErrorMessage
      v-if="error"
      :error="error"
    />
    
  </main>
</template>

<script>
import ErrorMessage from '../components/ErrorMessage.vue'
import WeatherData from '../components/WeatherData.vue'
import WeatherDataLoader from '../components/WeatherDataLoader.vue'
import MyCities from '../components/MyCities.vue'

export default {
  components: { WeatherData, WeatherDataLoader, ErrorMessage, MyCities },
  data() {
    return {
      search: '',
      data: null,
      loading: false,
      error: false,
      myCities: []
    }
  },
  mounted() {
    this.loadMyCities()
  },  
  methods: {
    showCityWeather(city){
      this.search = city
      this.searchWeather()
    },
    async searchWeather() {
      console.log(this.search);
      this.loading = true
      if( this.search.length < 3){
        this.$refs.searchInput.focus()
        return
      }

      const url = `https://forecast9.p.rapidapi.com/rapidapi/forecast/${this.search}/summary/`;
      const options = {
        method: 'GET',
        headers: {
          'X-RapidAPI-Key': import.meta.env.VITE_API_KEY,
          'X-RapidAPI-Host': 'forecast9.p.rapidapi.com'
        }
      };

      try {
        const response = await fetch(url, options);
        const result = await response.json();
        console.log(result);
        this.data = result
        this.search = ''
        this.loading = false
      } catch (error) {
        console.error(error);
        this.loading = false
        this.error = true
      }
    },
    loadMyCities() {
      const cities = localStorage.getItem('cities');
      this.myCities = cities ? JSON.parse(cities) : [];
    },
    saveNewCity(city) {
      if (this.myCities.includes(city)) {
        return;
      }
      this.myCities.push(city);
      localStorage.setItem('cities', JSON.stringify(this.myCities));
      console.log(city);
    },
    removeCity(city) {
      const index = this.myCities.indexOf(city);
      if (index !== -1) {
        this.myCities.splice(index, 1);
        localStorage.setItem('cities', JSON.stringify(this.myCities));
      }
    }
  }
}
</script>

<style>

</style>