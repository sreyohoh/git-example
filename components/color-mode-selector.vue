<template>
    <div class="flex space-x-2 items-center">
        <div class="text-gray-500" v-if="showNextModelLabel">Change to {{ nextMode }}</div>
        <button @click="toggleMode" @mouseenter="showNextModelLabel = true " @mouseleave="showNextModelLabel = false"  class="hover:bg-gray-200 dark:hover:bg-gray-600"> {{ nextMode }}</button>
    </div>
</template>
<script setup>
const showNextModelLabel = ref(false);
const colorMode = useColorMode()

const modes = [
    'system', // 0
    'light', // 1
    'dark', //2
]
const nextMode = computed(() => {
    const currentModeIndex = modes.indexOf(colorMode.preference);
    let nextModeIndex = null
    if (currentModeIndex + 1 == modes.length) {
        nextModeIndex = 0
    } else {
        nextModeIndex = currentModeIndex + 1
    }
    return modes[nextModeIndex];


})
const toggleMode = () => colorMode.preference = nextMode.value

</script>