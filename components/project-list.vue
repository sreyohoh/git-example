<template>
    <div>
        <section v-if="pending"> Pending...</section>
        <section v-else-if="error">Something wend wrong</section>
        <section v-else>
            <ul class="grid grid-cols-1 gap-4">
                <li v-for="item in repos" :key="item.id" class="border border-gray-200 rounded-sm p-4 hover:bg-gray-200">
                    <a :href="item.html_url" target="_blank">
                        <div class="flex items-center justify-between">
                            <div class="font-semibold">
                                {{ item.name }}
                            </div>
                            <div>
                                {{ item.stargazers_count }} *
                            </div>
                        </div>
                        <p class="text-sm">
                            {{ item.description }}
                        </p>
                    </a>
                </li>
            </ul>
        </section>
    </div>
</template>
<script setup>
const { error, pending, data } = await useFetch(
    'https://api.github.com/users/piotr-jura-udemy/repos'
)
const repos = computed(
    () => data.value.filter(repo => repo.description)
     .sort((a,b)=> b.stargazers_count - a.stargazers_count)
)
</script>