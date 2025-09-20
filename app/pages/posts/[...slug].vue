<script setup lang="ts">
const route = useRoute()
const { data: page } = await useAsyncData(route.path, () => {
    return queryCollection('posts').path(route.path).first()
})
</script>

<template>
    <UContainer>
        <main>
            <h1>{{ page.title }}</h1>
            <ContentRenderer v-if="page" :value="page" />
            <div class="py-6">
                <div>
                    <div><nuxt-link to="/posts"><- Back</nuxt-link></div>
                </div>
            </div>
        </main>
    </UContainer>
</template>
