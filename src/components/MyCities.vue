<template>
    <ul v-if="myCitiesList.length > 0" class="mb-8 flex gap-4">
      <li
        v-for="myCity in myCitiesList"
        :key="myCity"
        class="border rounded-lg min-w-[100px] md:min-w-[150px] w-fit flex items-center justify-around gap-2 p-2 bg-stone-950 cursor-pointer hover:bg-stone-900 text-lg md:text-xl font-bold"
      >
        <h3 @click="handleCitySearch(myCity)">{{ myCity }}</h3>
        <icon class="fa-solid fa-close" @click="handleDeleteCity(myCity)"></icon>
      </li>
    </ul>
    <span v-else class="flex mb-8">No cities on your list, search for a new one ↓ and add it to the list!</span>
  </template>
  
  <script>
  export default {
    props: ['myCitiesList'],
    methods: {
      handleCitySearch(city) {
        this.$emit('show-weather', city);
      },
      handleDeleteCity(city) {
        this.$emit('remove-city', city);
      },
    },
  };
  </script>
  