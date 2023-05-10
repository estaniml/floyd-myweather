<template>
  <Transition name="modal-outer">
    <div v-show="modalActive" class="absolute w-full bg-black bg-opacity-30 backdrop-blur-sm h-screen top-0 left-0 flex justify-center px-4 md:px-8">
        <Transition name="modal-inner">
            <div v-if="modalActive" class="p-4 bg-stone-900 self-start mt-16 md:mt-32 max-w-screen-md flex flex-col gap-5">
                <slot />
                <button 
                    class="text-white mt-8 bg-stone-500 py-2 px-6"
                    @click="$emit('close-modal')"
                >
                    Close
                </button>
            </div>
        </Transition>
    </div>
  </Transition>
</template>

<script>
export default {
    props: {
        modalActive: {
            type: Boolean,
            required: true,
            default: false,
        },
    }
}
</script>

<style scoped>
.modal-outer-enter-active, .modal-outer-leave-active {
    transition: opacity 0.3s cubic-bezier(0.52, 0.02, 0.19, 1);
}

.modal-outer-enter-from, .modal-outer-leave-to{
    opacity: 0;
}

.modal-inner-enter-active {
    transition: all 0.3s cubic-bezier(0.52, 0.02, 0.19, 1) 0.15s;
}

.modal-inner-leave-active {
    transition: all 0.3s cubic-bezier(0.52, 0.02, 0.19, 1);
}

.modal-inner-enter-from{
    opacity: 0;
    transform: scale(0.8);
}

.modal-inner-leave-to{
    transform: scale(0.8);
}

</style>