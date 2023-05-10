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
                <p>I’ve written a few thousand words on why traditional “semantic class names” are the reason CSS is hard to maintain, but the truth is you’re never going to believe me until you actually try it. If you can suppress the urge to retch long enough to give it a chance, I really think you'll wonder how you ever worked with CSS any other way.</p>
            </div>

            
            <div>
                <h3 class="text-xl mb-2 uppercase font-bold">Get city</h3>
                <p>Utility classes help you work within the constraints of a system instead of littering your stylesheets with arbitrary values. They make it easy to be consistent with color choices, spacing, typography, shadows, and everything else that makes up a well-engineered design system.</p>
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