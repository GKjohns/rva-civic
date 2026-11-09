<script setup lang="ts">
const widgets = [
  {
    icon: 'i-lucide-waves',
    tag: 'Fun',
    title: 'Is the James River good today?',
    description: 'River level, temperature and flow from the USGS gauge, turned into a plain answer for tubing, rafting or staying on the rocks.'
  },
  {
    icon: 'i-lucide-phone-call',
    tag: 'Important',
    title: 'What Richmond calls 311 about',
    description: 'Service requests by neighborhood and season. Potholes, trash, streetlights, and how long each takes to close.'
  },
  {
    icon: 'i-lucide-bus',
    tag: 'Getting around',
    title: 'GRTC by the numbers',
    description: 'Ridership by route and stop, and which lines do the heavy lifting.'
  },
  {
    icon: 'i-lucide-utensils',
    tag: 'Fun',
    title: 'Restaurant inspection leaderboard',
    description: 'Health inspection results across the city, searchable, with the cleanest kitchens on top.'
  },
  {
    icon: 'i-lucide-landmark',
    tag: 'Important',
    title: 'Where the city budget goes',
    description: 'The general fund broken into pieces you can click through, compared year over year.'
  },
  {
    icon: 'i-lucide-home',
    tag: 'Important',
    title: 'Housing and assessments',
    description: 'How property assessments have moved by neighborhood, and what that means for the tax bill.'
  }
]
</script>

<template>
  <div>
    <UPageHero
      title="Richmond, by the numbers"
      :description="SITE.description + ' Public data, small analyses, and a few things to play with.'"
      :links="[{
        label: 'See what\'s brewing',
        to: '#widgets',
        trailingIcon: 'i-lucide-arrow-down',
        size: 'xl'
      }, {
        label: 'Source on GitHub',
        to: SITE.repo,
        target: '_blank',
        icon: 'i-simple-icons-github',
        size: 'xl',
        color: 'neutral',
        variant: 'subtle'
      }]"
    />

    <UPageSection
      id="widgets"
      title="On the workbench"
      description="Ideas in progress. Each one becomes a small interactive widget backed by public data."
    >
      <div class="grid gap-4 sm:grid-cols-2 lg:grid-cols-3">
        <WidgetCard
          v-for="w in widgets"
          :key="w.title"
          v-bind="w"
          status="soon"
        />
      </div>
    </UPageSection>

    <UPageSection>
      <UPageCTA
        title="Got a question about Richmond?"
        description="If there's public data on it, it might make a good widget. Open an issue with the question you want answered."
        variant="subtle"
        :links="[{
          label: 'Suggest an idea',
          to: `${SITE.repo}/issues/new`,
          target: '_blank',
          trailingIcon: 'i-lucide-arrow-right',
          color: 'neutral'
        }]"
      />
    </UPageSection>
  </div>
</template>
