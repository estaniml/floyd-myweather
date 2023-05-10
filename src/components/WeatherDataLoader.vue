<template>
  <div class="p-10 bg-stone-900 rounded-lg h-[550px] md:h-[450px] relative overflow-hidden after:absolute after:content-[''] after:w-80 after:h-[200%] after:bg-stone-950 after:top-0 after:-left-20 after:blur-lg  after:-z-10 animate-skeleton animate-pulse">
    Loading..
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.animate-skeleton::after{
    animation-name: example;
    animation-duration: 1.5s;
    animation-timing-function: linear;
    animation-delay: .4s;
    animation-iteration-count: infinite;
}

@keyframes example {
    from {
        left: -50%;
    }
   to {
        left: 150%;
    }
}
</style>