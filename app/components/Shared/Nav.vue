<script
  setup
  lang="ts"
>
const appConfig = useAppConfig()
const siteName = appConfig.siteName
const siteLogo = appConfig.siteLogo
</script>

<template>
  <div class="fixed top-0 left-0 right-0 z-50 backdrop-blur-sm flex justify-between flex-row border-b">
    <div class="flex items-center">
      <NuxtLink
        class="font-bold px-2"
        to="/"
      >{{ siteLogo ? siteLogo : siteName }}</NuxtLink>
    </div>
    <div class="flex gap-8 items-center">
      <NuxtLink to="/">HOME</NuxtLink>
      <NuxtLink to="/about">ABOUT</NuxtLink>
      <NuxtLink to="/posts">BLOG</NuxtLink>
      <NuxtLink
        to="/contact"
        class="bg-white text-black px-4 py-2 h-full flex items-center hover:bg-gray-100 transition-colors duration-300"
      >
        CONTACT US
      </NuxtLink>
    </div>
  </div>
</template>

<style scoped></style>
