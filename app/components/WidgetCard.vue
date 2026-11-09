<script setup lang="ts">
defineProps<{
  title: string
  description: string
  icon: string
  tag?: string
  status?: 'live' | 'soon'
}>()
</script>

<template>
  <UCard
    class="h-full"
    :ui="{ body: 'flex h-full flex-col gap-3' }"
  >
    <div class="flex items-start justify-between gap-3">
      <UIcon
        :name="icon"
        class="size-7 text-primary"
      />
      <UBadge
        :label="status === 'live' ? 'Live' : 'Coming soon'"
        :color="status === 'live' ? 'primary' : 'neutral'"
        variant="subtle"
        size="sm"
      />
    </div>
    <div>
      <p
        v-if="tag"
        class="text-xs font-medium uppercase tracking-wide text-muted"
      >
        {{ tag }}
      </p>
      <h3 class="text-base font-semibold text-highlighted">
        {{ title }}
      </h3>
      <p class="mt-1 text-sm text-muted">
        {{ description }}
      </p>
    </div>
    <div class="mt-auto">
      <slot />
    </div>
  </UCard>
</template>
