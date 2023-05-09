<template>
  <div class="bg-black border-t border-stone-800 py-10 text-stone-400 text-sm">
    <div class="flex gap-3 justify-center">
        <p>This project was created by: </p>
        <a 
            href="https::/emlacabe.vercel.app"
            target="_blank"
            class="font-bold text-gradient text-animation"
        >Estanislao Martinez Lacabe, Frontend Developer</a>
    </div>
  </div>
</template>

<style scoped>
.text-gradient {
    background: -webkit-linear-gradient(45deg, #12f0a6, #4e45f3);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    position: relative;
}

.text-animation::after{
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0%;
    height: 2px;
    background: linear-gradient(90deg, #10b981, #4f46e5);
    transition: all 0.5s ease-in-out;
}

.text-animation:hover::after{
    width: 100%;
    transition: all 0.5s ease-in-out;
}
</style>
