<script setup lang="ts">
useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: '/favicon.ico' }
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

useSeoMeta({
  title: SITE.name,
  description: SITE.description,
  ogTitle: SITE.name,
  ogDescription: SITE.description,
  twitterCard: 'summary'
})
</script>

<template>
  <UApp>
    <UHeader>
      <template #left>
        <NuxtLink
          to="/"
          class="focus-visible:outline-3 outline-primary/25 rounded-md p-1 -ms-1"
        >
          <AppLogo />
        </NuxtLink>
      </template>

      <template #right>
        <UColorModeButton />

        <UButton
          :to="SITE.repo"
          target="_blank"
          icon="i-simple-icons-github"
          aria-label="GitHub"
          color="neutral"
          variant="ghost"
        />
      </template>
    </UHeader>

    <UMain>
      <NuxtPage />
    </UMain>

    <USeparator icon="i-lucide-waves" />

    <UFooter>
      <template #left>
        <p class="text-sm text-muted">
          {{ SITE.name }} • Made in Richmond, VA • © {{ new Date().getFullYear() }}
        </p>
      </template>
    </UFooter>
  </UApp>
</template>
