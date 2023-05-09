<template>
  <main class="pt-10 bg-black min-h-screen">
    <h2 class="mb-4 text-2xl text-emerald-500 font-bold">★ Your cities</h2>
    <ul class="mb-8 flex gap-4">
      <li class="border rounded-lg min-w-[150px] w-fit flex items-center justify-around gap-2 p-2 bg-stone-950 cursor-pointer hover:bg-stone-900">
        <h3 class="text-xl font-bold">Parana</h3>
      </li>
      <li class="border rounded-lg min-w-[150px] w-fit flex items-center justify-around gap-2 p-2 bg-stone-950 cursor-pointer hover:bg-stone-900">
        <h3 class="text-xl font-bold">Raleigh</h3>
      </li>
    </ul>

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
    />
    
  </main>
</template>

<script>
import WeatherData from '../components/WeatherData.vue'

export default {
  components: { WeatherData },
  data() {
    return {
      search: '',
      data: null
    }
  },
  mounted() {
  },
  methods: {
    async searchWeather() {
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
      } catch (error) {
        console.error(error);
      }
    }
  }
}
</script>

<style>

</style>