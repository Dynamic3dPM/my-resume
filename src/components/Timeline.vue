<template>
    <v-container class="pa-md-12 custom-background">
      <v-card class="mx-auto pa-6" max-width="900" rounded="lg">
        <v-timeline align-top dense>
          <v-timeline-item
            v-for="(event, index) in events"
            :key="index"
            :class="index % 2 === 0 ? 'text-start' : 'text-end'"
            :color="event.color"
            dot-color="primary"
            fill-dot
            :icon="event.icon"
          >
            <div>
              <h3>{{ event.title }}</h3>
              <em>{{ event.date }}</em>
              <p>{{ event.description }}</p>
            </div>
          </v-timeline-item>
        </v-timeline>
      </v-card>
    </v-container>
  </template>
  
  <script setup>
  const events = [
    {
      title: 'Planning Begins',
      date: 'April 7, 2025',
      description: 'Today I start preparing for SkillBridge, terminal leave, and my transition to civilian life.',
      color: 'orange',
      icon: 'mdi-calendar-start',
    },
    {
      title: 'Eligible for SkillBridge',
      date: 'October 23, 2025',
      description: 'Start of my 90-day SkillBridge program to gain skills and explore job opportunities.',
      color: 'blue',
      icon: 'mdi-briefcase',
    },
    {
      title: 'Permissive TDY Begins',
      date: 'January 21, 2026',
      description: '30 days of permissive TDY to job hunt and finalize my transition plans.',
      color: 'purple',
      icon: 'mdi-home-search',
    },
    {
      title: 'Terminal Leave Starts',
      date: 'February 20, 2026',
      description: 'Begin 70 days of terminal leave, wrapping up military service and starting job applications.',
      color: 'green',
      icon: 'mdi-calendar-check',
    },
    {
      title: 'Retirement & Job Opportunities',
      date: 'April 30, 2026',
      description: 'Officially retired! Ready to start my new career with skills gained from SkillBridge.',
      color: 'red',
      icon: 'mdi-party-popper',
    },
  ];
  </script>
  
  <style scoped lang="scss">
  @use '@/styles/settings.scss' as *;
  
  // Apply the custom background to the container
  .custom-background {
    background-color: $custom-background-color-light;
    width: 100%; // Stretch background across the container
  }
  
  // Apply font to h1 (not used in this component)
  h1 {
    font-family: $font-family-times;
  }
  
  // Apply font to h2 (not used in this component)
  h2 {
    font-family: $font-family-times;
  }
  
  // Apply font to h3 (used for event titles)
  h3 {
    font-family: $font-family-times;
  }
  
  // Apply font to all <p> elements
  p {
    font-family: $font-family-open-sans;
  }
  
  // Apply font to <em> elements (used for dates)
  em {
    font-family: $font-family-open-sans;
  }
  </style>