<template>
    <div>
        <h1>About Us</h1>
        <button @click="enableCustomLayout()">
            Another layout
        </button>
    </div>
</template>
<script setup>
// definePageMeta({
//     layout: "another"
// })
function enableCustomLayout() {
    setPageLayout( "another" );
}
</script>