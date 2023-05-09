<template>
  <div class="p-10 border border-stone-800 bg-stone-900 rounded-lg">
    <div class="flex justify-between gap-2">
      <div>
        <h2 class="text-4xl"><i class="fa-solid fa-location-dot"></i> Buenos Aires</h2>
        <div class="flex items-center justify-esnd mt-4 gap-2">
          <span>Lat: 32 º</span>
          <span>Long: 32 º</span>
        </div>
        <button 
          class="border border-emerald-300 text-emerald-400 mt-4 flex items-center gap-2 px-2 rounded-full w-8 overflow-hidden h-8 hover:w-48 hover:bg-emerald-500 hover:text-white transition-all duration-300 ease-linear whitespace-nowrap"
        ><strong class="text-4xl ">+</strong> Add to your cities</button>
      </div>

      <div class="">
        <div class="flex justify-between">
          <p class="text-xl text-stone-300"><i class="fa-solid fa-calendar-days"></i> Date: 2019-01-25</p>
          <p class="text-lg text-stone-300"><i class="fa-solid fa-square-up-right"></i> Source: The weather </p>
        </div>

        <div class="flex gap-4">
          <div class="flex items-center justify-end mt-4 gap-4 text-xl bg-gradient-to-bl from-stone-950 to-stone-800 p-4 rounded-lg">
            <span><strong class="text-6xl">32</strong> º max</span>
            <span><strong class="text-6xl">22</strong> º min</span>
          </div>

          <div class="flex items-center justify-end mt-4 gap-4 text-xl bg-gradient-to-bl from-stone-950 to-stone-900 p-4 rounded-lg">
            <span><strong class="text-6xl">10</strong>% <i class="fa-solid fa-cloud-rain text-xl"></i></span>
            <span><strong class="text-6xl">22</strong>km/h <i class="fa-solid fa-wind text-xl"></i></span>
          </div>
        </div>
      </div>
    </div>

    <ul class="mt-10 py-4 flex gap-4 overflow-x-auto">
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Miercoles
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Jueves
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Viernes
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Sabado
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i>  Domingo
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Lunes
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Martes
        </div>

        <div class="flex gap-2 text-sm">
          <span><strong class="text-3xl">32</strong>º max</span>
          <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
          <i class="fa-solid fa-sun text-xl text-white"></i> Mierc
        </div>

        <div class="flex gap-2 text-sm">
            <span><strong class="text-3xl">32</strong>º max</span>
            <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
           <i class="fa-solid fa-sun text-xl text-white"></i> Mierc
        </div>

        <div class="flex gap-2 text-sm">
            <span><strong class="text-3xl">32</strong>º max</span>
            <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
      <li class="w-fit min-w-[150px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 p-4 rounded-lg cursor-pointer border border-stone-800 hover:border-white">
        <div>
           <i class="fa-solid fa-sun text-xl text-white"></i> Mierc
        </div>

        <div class="flex gap-2 text-sm">
            <span><strong class="text-3xl">32</strong>º max</span>
            <span><strong class="text-3xl">22</strong>º min</span>
          </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
    props: ['data'],
    data() {
      return {
        day: 1
      }
    },
    mounted() {
      console.log(this.data);
    }
}
</script>

<style>

</style>