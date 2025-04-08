<template>
  <v-container class="pa-sm-9 pa-md-12" fluid>
    <div class="text-center mb-md-12 mb-6">
      <v-avatar
        class="mb-6 avatar-custom"
        color="primary"
        rounded
        size="160"
      >
        <img 
          src="@/assets/1696383167109.jpeg" 
          alt="Tim Carrender Profile Image" 
          class="w-100 h-100"
        />
      </v-avatar>
      <p class="font-weight-medium text-primary">What Sets Me Apart</p>
      <h2 class="text-h5 font-weight-bold mb-2 text-sm-h4">Core Professional Strengths</h2>
      <v-divider class="mx-auto" length="48" thickness="4" />
    </div>

    <v-row justify="center">
      <v-col
        v-for="(item, i) in items"
        :key="i"
        cols="12"
        md="4"
        class="d-flex"
      >
        <v-responsive
          class="mx-auto text-left"
          max-width="400"
          width="100%"
        >
          <v-list-item class="px-0 align-start">
            <template #prepend>
              <v-icon 
                :icon="item.icon" 
                size="36" 
                color="primary" 
                class="mr-4 opacity-75"
              />
            </template>
            <template #title>
              <span class="text-subtitle-1 font-weight-semibold">{{ item.title }}</span>
            </template>
            <template #subtitle>
              <span class="text-caption text-primary font-weight-medium">{{ item.subtitle }}</span>
            </template>
            <p class="text-body-2 text-medium-emphasis mt-2">
              {{ item.content }}
            </p>
          </v-list-item>
          <v-divider class="mt-4 mb-6" color="primary" length="48" thickness="2" />
        </v-responsive>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
  const items = [
    {
      title: 'Proven Project Leadership',
      subtitle: 'PMP® Certified with 18+ Years of Experience',
      content: 'I spearhead complex projects with precision, delivering on time and within budget. My PMP certification and nearly two decades in the U.S. Army fuel my ability to manage agile software initiatives and create impactful solutions like the globally-used Ask Chief app.',
      icon: 'mdi-briefcase-check',
    },
      {
    title: 'Network & Cybersecurity Expertise',
    subtitle: 'Security+ Certified Network Specialist',
    content: 'As an Army network manager, I oversee the setup and maintenance of critical communication networks, ensuring secure data flow across local and global systems. I configure equipment like Brocade, Juniper, and Cisco, troubleshoot issues, and implement protections to keep operations running and safe from cyber attacks.',
    icon: 'mdi-shield-lock',
  },
    {
      title: 'AI-Powered Full-Stack Solutions',
      subtitle: 'AWS, Flutter, Vue.js, and Beyond',
      content: 'As the founder of TK Ingenuity Solutions, I build scalable, cloud-native applications with AI integration, leveraging AWS, Flutter, Expo, Vue.js, Python, Docker, React, and React Native to turn visionary ideas into reality.',
      icon: 'mdi-robot', // Represents AI and advanced tech
    },
  ]
</script>

<style scoped lang="scss">
@use '@/styles/settings.scss' as *;

.custom-background {
  background-color: $custom-background-color;
}

h1 {
  font-family: $font-family-times;
}

h2 {
  font-family: $font-family-times;
}

p {
  font-family: $font-family-open-sans;
}
</style>