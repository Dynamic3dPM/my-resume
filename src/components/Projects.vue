<template>
    <v-container
      class="pa-md-12 pa-sm-7 pb-12 custom-background"
      fluid
      elevation="2"
    >
      <v-responsive
        class="text-center mx-auto mb-6 mb-md-12"
        max-width="700"
      >
        <p class="font-weight-medium text-primary">My Work</p>
        <h1 class="text-h4 font-weight-bold mb-4">
          Projects Past and Present
        </h1>
        <p class="text-subtitle-1 text-medium-emphasis">
          A showcase of my technical expertise and innovative solutions, from military tools to cutting-edge applications.
        </p>
      </v-responsive>
  
      <div class="d-flex justify-center mb-6 mx-auto">
        <v-sheet
          class="pa-1"
          rounded="xl"
          elevation="2"
        >
          <v-btn
            class="mr-1 text-none"
            :color="selectedFilter == 'current' ? 'primary' : 'default'"
            rounded
            text="Current"
            variant="flat"
            @click="handleChangeFilter('current')"
          />
          <v-btn
            class="text-none"
            :color="selectedFilter == 'past' ? 'primary' : 'default'"
            rounded
            text="Past"
            variant="flat"
            @click="handleChangeFilter('past')"
          />
        </v-sheet>
      </div>
  
      <v-row
        :justify="filteredProjects.length === 1 ? 'center' : 'start'"
        class="flex-nowrap flex-md-wrap"
      >
        <v-col
          v-for="(project, i) in filteredProjects"
          :key="i"
          cols="12"
          lg="4"
          md="6"
          sm="12"
        >
          <v-card
            border
            class="pa-8 d-flex flex-column mx-auto"
            flat
            height="600"
            max-width="450"
            rounded="xl"
          >
            <p class="mb-2 font-weight-bold">{{ project.title }}</p>
            <v-img
              :src="project.image"
              :alt="`${project.title} Project Image`"
              height="100"
              class="mb-3"
              contain
            />
            <p class="text-subtitle-2 pb-3">{{ project.subtitle }}</p>
            <p class="text-body-1 mb-4 font-weight-medium">{{ project.duration }}</p>
            <v-list-item
              v-for="(highlight, index) in project.highlights"
              :key="index"
              class="px-0 text-body-2"
            >
              <v-icon
                class="mr-1"
                :color="project.status === 'current' ? 'primary' : 'default'"
                :icon="project.icons[index]"
              />
              {{ highlight }}
            </v-list-item>
            <v-btn
              v-if="project.link"
              class="mt-4 text-none mx-auto"
              :color="project.status === 'current' ? 'primary' : 'black'"
              max-height="36"
              text="Visit Site"
              variant="flat"
              width="50%"
              :href="project.link"
              target="_blank"
            />
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script setup>
    import { shallowRef, computed } from 'vue';
  
    // Import images as modules
    import ffpInvestImage from '@/assets/ffpinvest.png';
    import pmpStudyGuideImage from '@/assets/pmp-study-guide.png';
    import askChiefImage from '@/assets/chief.png';
    import cryptoSecureVaultImage from '@/assets/crypto-secure.jpeg';
    import saddlefitImage from '@/assets/saddlefit.png';
    import maiddayImage from '@/assets/Maid_Logo.png'; 
  
    const selectedFilter = shallowRef('current');
  
    const handleChangeFilter = (value) => {
      selectedFilter.value = value;
    };
  
    const projects = [
      {
        title: 'FFP Invest Alert & Newsletter System',
        subtitle: 'Project Manager & Lead Developer',
        duration: 'OCT 2024 - Present',
        status: 'current',
        link: 'https://ertch.com',
        image: ffpInvestImage,
        highlights: [
          'Leading React Native mobile app development for alerts and newsletters.',
          'Integrating AWS AppSync, DynamoDB, and GraphQL with backend team.',
          'Implementing Stripe payments and AWS Cognito for secure authentication.',
          'Deploying serverless architecture using AWS Serverless Framework.',
        ],
        icons: [
          'mdi-cellphone',
          'mdi-database',
          'mdi-credit-card',
          'mdi-cloud-upload',
        ],
      },
      {
        title: 'PMP Audio Study Guide',
        subtitle: 'Mobile App for PMP Exam Prep',
        duration: 'Jul 2023 - Jul 2024',
        status: 'past',
        image: pmpStudyGuideImage,
        highlights: [
          'Developed with Flutter for cross-platform use.',
          'Features audio-visual lessons and mindset coaching.',
          'Published on Apple and Google Play stores.',
          'Sunset 2023 on both platforms.',
        ],
        icons: [
          'mdi-flutter',
          'mdi-headphones',
          'mdi-store',
          'mdi-archive',
        ],
      },
      {
        title: 'Ask Chief App',
        subtitle: 'Global Tool for U.S. Army Soldiers',
        duration: 'Past Project (Completed)',
        status: 'past',
        image: askChiefImage,
        highlights: [
          'Crafted a fine-tuned LLM with Flutter for soldier support, pre-dating ChatGPT.',
          'Enabled global access to AI-driven insights for soldiers.',
          'Deployed scalable infrastructure to support worldwide use.',
          'Demonstrated early leadership in mobile AI innovation.',
        ],
        icons: [
          'mdi-robot',
          'mdi-earth',
          'mdi-server',
          'mdi-lightbulb-on',
        ],
      },
      {
        title: 'Crypto Secure Vault',
        subtitle: 'Cybersecurity Business Solution',
        duration: 'Nov 2017 - Jun 2019',
        status: 'past',
        link: null,
        image: cryptoSecureVaultImage,
        highlights: [
          'Founded a business focused on data breach prevention.',
          'Utilized AWS for secure infrastructure.',
          'Provided consultations using Python and network expertise.',
          'Protected client assets with a "everyone deserves protection" ethos.',
        ],
        icons: [
          'mdi-briefcase',
          'mdi-cloud-lock',
          'mdi-code-braces',
          'mdi-shield-check',
        ],
      },
      {
        title: 'SaddleFit',
        subtitle: 'Project Manager & Lead IT',
        duration: 'Sep 2023 - Present',
        status: 'current',
        link: 'https://saddlefit.io',
        image: saddlefitImage,
        highlights: [
          'Overseeing development of C++ and C# software for 3D scanning technology.',
          'Leading creation of a React-based custom website for saddle fitting and shopping.',
          'Revolutionizing the equine industry with innovative tech solutions.',
          'Ensuring project completion through effective management and IT leadership.',
        ],
        icons: [
          'mdi-code-tags',
          'mdi-web',
          'mdi-horse',
          'mdi-briefcase-check',
        ],
      },
      {
  title: 'MaidDay App',
  subtitle: 'Project Manager & Lead Developer',
  duration: 'March 2025 - Present',
  status: 'current',
  image: maiddayImage, 
  highlights: [
    'Developing a gig-style app with React Native for maid service booking and tracking.',
    'Implementing geo-fencing to connect customers with nearby maids efficiently.',
    'Streamlining the bid process based on personal hiring experience.',
    'Building a comprehensive platform to enhance service delivery for maids.',
  ],
  icons: [
    'mdi-cellphone',         // App development (React Native)
    'mdi-map-marker-radius', // Geo-fencing
    'mdi-handshake',         // Bid process
    'mdi-broom',             // Maid service focus
  ],
},
    ];
  
    const filteredProjects = computed(() => {
      return projects.filter(project => project.status === selectedFilter.value);
    });
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