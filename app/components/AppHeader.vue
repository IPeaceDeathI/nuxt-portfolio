<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const route = useRoute()

const items = computed<NavigationMenuItem[]>(() => [
  {
    label: 'Docs',
    to: '/docs/getting-started',
    active: route.path.startsWith('/docs/getting-started'),
  },
  {
    label: 'Components',
    to: '/docs/components',
    active: route.path.startsWith('/docs/components'),
  },
  {
    label: 'R6 Stats',
    to: 'https://r6.tracker.network/r6siege/profile/ubi/Peace__Death/overview',
    target: '_blank',
  },
])
</script>

<template>
  <UHeader>
    <template #title>
      <UTooltip text="Boiko Denis">
        <UButton
          to="https://github.com/IPeaceDeathI"
          target="_blank"
          variant="link"
        >
          <UAvatar src="https://github.com/IPeaceDeathI.png" icon="i-lucide-image" size="xl" loading="lazy" />
        </UButton>
      </UTooltip>
    </template>

    <UNavigationMenu :items="items" />

    <template #right>
      <UTooltip text="Change Theme">
        <UColorModeButton />
      </UTooltip>

      <UTooltip text="Open on GitHub">
        <UButton
          color="neutral"
          variant="ghost"
          to="https://github.com/IPeaceDeathI/nuxt-portfolio"
          target="_blank"
          icon="i-simple-icons-github"
          aria-label="GitHub"
        />
      </UTooltip>
    </template>
  </UHeader>
</template>
