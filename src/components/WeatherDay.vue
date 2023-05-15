<template>
    <li 
        :class="[ isActive 
            ? 'w-fit min-w-[180px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 py-4 px-2 rounded-lg cursor-pointer border border-emerald-500'
            : 'w-fit min-w-[180px] flex flex-col items-center justify-end mt-4 gap-4 text-xl bg-stone-800 text-stone-400 py-4 px-2 rounded-lg cursor-pointer border border-stone-800 hover:border-white hover:-translate-y-2 transition-all duration-200 ease-linear'
        ]"
    >
        <div class="flex items-center gap-2">
            <span v-if="this.day.weather.text === 'wolkig'">
                <i class="fa-solid fa-cloud text-xl text-white"></i>
            </span> 
            <span v-else-if="this.day.weather.text === 'bedeckt'">
                <i class="fa-solid fa-cloud text-xl text-white"></i>
            </span> 
            <span v-else-if="this.day.weather.text === 'klar' ">
                <i class="fa-solid fa-sun text-xl text-white"></i>
            </span>
            <span v-else-if="this.day.weather.text === 'sonnig'">
                <i class="fa-solid fa-sun text-xl text-white"></i>
            </span>  
            <span v-else>
                <i class="fa-solid fa-cloud-rain text-xl text-white"></i>
            </span> 
            {{getNameDay}}
        </div>

        <div class="flex gap-2 text-sm">
            <span><strong class="text-3xl">{{this.day.temperature.max}}</strong> º max</span>
            <span><strong class="text-3xl">{{this.day.temperature.min}}</strong> º min</span>
        </div>
    </li>
</template>

<script>
import moment from 'moment'

export default {
    props: ['key', 'day', 'isActive'],
    computed: {
        getNameDay() {
            return moment(this.day.date).format('dddd')
        },
        
    },
    mounted() {
        console.log(this.key, 'id');
        console.log(this.isActive, 'cw');
        console.log(this.day, 'cw');
    }
}
</script>

<style>

</style>