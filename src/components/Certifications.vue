<template>
    <v-container class="pa-md-12 pa-sm-6 pe-md-0 custom-background" fluid>
      <v-row justify="center">
        <v-col cols="12" md="5">
          <p class="font-weight-medium text-primary">Project Management Expertise</p>
  
          <p class="mt-2 text-h5 font-weight-bold text-sm-h4 custom-title">
            Bridging the Gap Between Teams
          </p>
  
          <p class="my-4 text-body-1 text-medium-emphasis">
            As a PMP and Security+ certified project manager with full-stack development skills, I ensure projects are delivered on time and to specification by speaking the language of developers and stakeholders alike.
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
              <p class="text-body-2 font-weight-bold pb-2">
                {{ item.title }}
              </p>
            </template>
          </v-list-item>
        </v-col>
  
        <v-col class="d-flex align-center justify-center" cols="12" md="6" offset-md="1">
          <v-fade-transition>
            <v-img
              :key="currentImageIndex"
              :src="images[currentImageIndex].src"
              :alt="images[currentImageIndex].alt"
              max-height="400"
              max-width="400"
              contain
              :rounded="$vuetify.display.smAndDown ? true : 's-lg'"
            />
          </v-fade-transition>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue';
  import { useTheme } from 'vuetify';
  
  // Use theme to toggle between dark/light mode (if needed)
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
  
  // Manage the current image index for cycling
  const currentImageIndex = ref(0);
  
  // Set up a timer to cycle images every 5 seconds
  let imageCycleTimer = null;
  onMounted(() => {
    imageCycleTimer = setInterval(() => {
      currentImageIndex.value = (currentImageIndex.value + 1) % images.length;
    }, 5000); // 5000ms = 5 seconds
  });
  
  // Clean up the timer when the component is unmounted
  onUnmounted(() => {
    if (imageCycleTimer) {
      clearInterval(imageCycleTimer);
    }
  });
  
  // Define features highlighting your capabilities
  const features = [
    {
      title: 'Certified Project Leadership',
      subtitle: 'PMP certification ensures disciplined project management, delivering projects on time and within budget.',
      icon: 'mdi-account-tie',
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
  ];
  </script>
  
  <style scoped lang="scss">
  @use '@/styles/settings.scss' as *;
  
  // Apply the custom background to the container
  .custom-background {
    background-color: $custom-background-color;
  }
  
  // Style the main title (equivalent to h1)
  .custom-title {
    font-family: $font-family-times;
    text-align: center;
    margin-bottom: 2rem;
  }
  
  // Apply font to h2 (not used in this component)
  h2 {
    font-family: $font-family-times;
  }
  
  // Apply font to all <p> elements
  p {
    font-family: $font-family-open-sans;
  }
  </style>