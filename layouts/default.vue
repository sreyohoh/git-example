<template>
    <div class="container mx-auto max-w-2xl">
        <header class="flex justify-between items-center">
            <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">Demo</NuxtLink>
            <nav>
                <ul class="flex space-x-4">
                    <li>
                        <NuxtLink to="/"> Home </NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/about"> About </NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/proect"> About </NuxtLink>
                    </li>
                </ul>
            </nav>
            <colorModeSelector />
        </header>
        <main class="p-2">
            <slot />
        </main>
    </div>
</template>
<script setup>

</script>
<style>
body {
  @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300
}
</style>