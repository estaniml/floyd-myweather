<template>
  <header class="flex justify-between items-center h-20 bg-black border-b border-stone-700 px-2">
    <RouterLink :to="{name: 'home'}">
        <div class="md:text-lg tracking-widest uppercase">
            <strong>Floyd</strong> <span class="font-light">My Weather </span>
            <i class="fa-solid fa-wind text-xl"></i>
        </div>
    </RouterLink>

    <nav class="flex items-center gap-4">
        <i 
            class="fa-solid fa-circle-info text-xl cursor-pointer hover:text-emerald-400"
            @click="setModalActive"
        ></i>
        <a
            href="https://github.com/estaniml/floyd-myweather" 
            target="_blank"
            class="md:border rounded-lg md:px-2 md:py-1 text-sm flex items-center md:gap-2 hover:bg-white hover:text-black font-bold transition-all duration-300 ease-linear"
        >
            <span class="hidden md:inline-block">See repository</span>
            <i class="fa-brands fa-github text-xl md:text-md"></i>
        </a>
        <HelpModal
            :modalActive="modalActive"
            @close-modal="setModalActive"
        >
            <div>
                <h1 class="text-xl mb-2 uppercase font-bold">About</h1>
                <p>Web app created with: <span class="text-emerald-300">Vue + Vue router + Tailwind + Forecast API</span></p>
            </div>
            
            <div>
                <h2 class="text-xl mb-2 uppercase font-bold">How it works</h2>
                <p>The web app utilizes the Forecast API to provide users with convenient access to weather information. Users can easily search for any city and retrieve the weather forecast for the day as well as upcoming days. Additionally, it offers a personalized feature that allows users to create a list of their favorite cities for quick and easy access. By simply adding cities to their saved list, users can stay updated on the weather conditions of multiple locations with just a few clicks.</p>
            </div>

            
            <div>
                <h3 class="text-xl mb-2 uppercase font-bold">See more</h3>
                <div class="flex flex-col gap-2">
                    <a href="https://github.com/estaniml/floyd-myweather" class="flex items-center gap-2 text-stone-300 hover:text-emerald-400">
                        <i class="fa-brands fa-github text-xl md:text-md"></i>
                        Github Repository
                    </a>
                    <a href="https://emlacabe.vercel.app" class="flex items-center gap-2 text-stone-300 hover:text-emerald-400">
                        <i class="fa-solid fa-e text-xl md:text-md"></i>
                        My Portfolio
                    </a>
                    <a href="https://www.linkedin.com/in/emartinezlacabe/" class="flex items-center gap-2 text-stone-300 hover:text-emerald-400">
                        <i class="fa-brands fa-linkedin text-xl md:text-md"></i>
                        My Linkedin
                    </a>
                </div>
            </div>
        </HelpModal>
    </nav>
  </header>
</template>

<script>
import HelpModal from './HelpModal.vue'

export default {
    components: { HelpModal },
    data() {
        return {
            modalActive: false
        }
    },
    methods: {
        setModalActive(){
            this.modalActive = !this.modalActive
        }
    }
}
</script>