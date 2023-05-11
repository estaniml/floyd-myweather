<template>
  <div class="border border-red-800 p-5 bg-stone-950 rounded-lg w-fit flex items-center mx-auto gap-4">
    <i class="fa-sharp fa-solid fa-circle-exclamation text-xl text-red-600"></i>
    <p>Server Error! Try again later</p>
  </div>
</template>

<script>
export default {
    props: {
        error: {
          required: true,
          default: 'You have exceeded the DAILY quota for Requests on your current plan, BASIC. Upgrade your plan at https://rapidapi.com/wettercom-wettercom-default/api/forecast9'
        }
    },
}
</script>

<style>

</style>