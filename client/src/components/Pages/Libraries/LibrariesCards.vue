<script setup>
import Card from 'primevue/card'
import Button from 'primevue/button'

const props = defineProps({
  data: Array
})
</script>

<template>
    <Card v-for="item in data" class="mx-4 my-4" style="width: 25em">
        <template #header>
            <div class="overflow-hidden">
                <div class="bg-contain bg-no-repeat bg-center h-20rem w-full" :style="{ backgroundImage: `url(${item.logo})` }"></div>
            </div>
        </template>
        <template #title> {{ item.name }} </template>
        <template #subtitle> {{ item.language }} - {{ item.latest_version }}</template>
        <template #content>
            <p>
                {{ item.description }}
            </p>
        </template>
        <template #footer>
            <a :href="item.github" target="_blank"><Button icon="pi pi-github" class="mx-2" /></a>
            <a :href="item.website" target="_blank"><Button icon="pi pi-external-link" class="mx-2" /></a>
            <a :href="item.pypi" target="_blank"><Button icon="pi pi-file" class="mx-2" /></a>
        </template>
    </Card>
</template>

<style scoped>
</style>
