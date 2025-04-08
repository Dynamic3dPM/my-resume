<template>
  <v-container class="pa-md-12 pa-sm-6 pe-md-0 custom-background" fluid>
    <v-row justify="center">
      <v-col cols="12" md="5">
        <p class="font-weight-medium text-primary">Project Management Expertise</p>
        <p class="mt-2 text-h5 font-weight-bold text-sm-h4 custom-title">
          Bridging the Gap Between Teams
        </p>
        <p class="my-4 text-body-1 text-medium-emphasis">
          As a PMP and Security+ certified project manager with full-stack development skills and 20 years of military service as a CW3, I ensure projects are delivered on time and to specification by speaking the language of developers and stakeholders alike.
        </p>
        <v-list-item
          v-for="(item, i) in features"
          :key="i"
          class="px-0 py-2"
          :subtitle="item.subtitle"
        >
          <template #prepend>
            <v-icon class="mr-2" color="primary" :icon="item.icon" size="small"></v-icon>
          </template>
          <template #title>
            <p class="text-body-2 font-weight-bold pb-2">{{ item.title }}</p>
          </template>
        </v-list-item>
      </v-col>

      <v-col class="d-flex align-center justify-center" cols="12" md="6" offset-md="1">
        <div class="collage-wrapper">
          <v-img
            v-for="(image, index) in images"
            :key="index"
            :src="image.src"
            :alt="image.alt"
            class="collage-image"
            contain
            :rounded="$vuetify.display.smAndDown ? true : 's-lg'"
          />
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { computed } from 'vue';
import { useTheme } from 'vuetify';

const theme = useTheme();

// Import the PMP and Security+ logos from the assets folder
const images = [
  {
    src: new URL('../assets/pmp.png', import.meta.url).href,
    alt: 'PMP Certification Logo',
  },
  {
    src: new URL('../assets/security+.png', import.meta.url).href,
    alt: 'Security+ Certification Logo',
  },
];

// Define features highlighting your capabilities
const features = [
  {
    title: 'University of Louisville',
    subtitle: 'CompTIA instructor teaching over 200 students in the last 5 years.',
    icon: 'mdi-school-outline',
  },
  {
    title: 'Certified Project Leadership',
    subtitle: 'PMP certification ensures disciplined project management, delivering projects on time and within budget.',
    icon: 'mdi-account-tie',
  },
  {
    title: '20 Years of Military Service',
    subtitle: 'Extensive experience in high-pressure environments, ensuring effective communication and collaboration. Holding multiple ranks throughout my career.',
    icon: 'mdi-tank',
  },
  {
    title: 'Full-Stack Development Skills',
    subtitle: 'Proficient in front-end and back-end technologies, enabling seamless communication with development teams.',
    icon: 'mdi-code-tags',
  },
  {
    title: 'Security Expertise',
    subtitle: 'Security+ certification ensures secure project practices, safeguarding data and systems.',
    icon: 'mdi-shield-lock-outline',
  },
  {
    title: 'Agile Methodologies',
    subtitle: 'Experience with Agile practices, ensuring flexibility and adaptability in project management.',
    icon: 'mdi-swap-horizontal',
  },
];
</script>

<style scoped lang="scss">
@use '@/styles/settings.scss' as *;

.custom-background {
  background-color: $custom-background-color;
}

.custom-title {
  font-family: $font-family-times;
  text-align: center;
  margin-bottom: 2rem;
}

h2 {
  font-family: $font-family-times;
}

p {
  font-family: $font-family-open-sans;
}

/* Collage container styling */
.collage-wrapper {
  display: flex;
  flex-wrap: wrap;
  gap: 15px; /* Space between images */
  justify-content: center;
}

/* Individual collage image styling */
.collage-image {
  width: 180px;
  height: 180px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
</style>
