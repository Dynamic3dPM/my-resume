<template>
  <v-layout>
    <v-main>
      <!-- Background Image with Overlay -->
      <div class="hero-section">
        <v-img
          cover
          height="400"
          src="@/assets/high-quality-desktop-wallpaper.jpg"
          class="hero-image"
        >
          <div class="overlay"></div>
        </v-img>
      </div>

      <v-container fluid class="profile-container">
        <!-- Breadcrumbs -->
        <v-breadcrumbs :items="items" class="mb-6">
          <template #prepend>
          </template>
        </v-breadcrumbs>

        <!-- Profile Section -->
        <div class="profile-card">
          <v-avatar class="profile-avatar" image="@/assets/1696383167109.jpeg" size="140" />

          <h1 class="text-h3 font-weight-bold text-white mb-2">Tim Carrender</h1>

          <div class="text-subtitle-1 font-weight-medium text-primary mb-6">Technical Project Manager</div>

          <div class="d-flex flex-wrap justify-center gap-3">
            <v-btn
              color="primary"
              rounded="pill"
              variant="flat"
              size="large"
              :href="'mailto:tim.carrender@gmail.com'"
              class="action-btn"
            >
              Email Me
            </v-btn>
            <v-btn
              color="secondary"
              rounded="pill"
              variant="flat"
              size="large"
              :href="'https://louisville.edu/education/departments/eleod/skills/c4/files/tim-carrender-article.pdf'"
              target="_blank"
              class="action-btn"
            >
              UofL Article
            </v-btn>
            <v-btn
              color="white"
              rounded="pill"
              variant="outlined"
              size="large"
              :href="'https://testimonials-photos-public.s3.us-east-1.amazonaws.com/TimCarrenderResume.pdf'"
              download
              target="_blank"
              class="action-btn"
            >
              Download Resume
            </v-btn>
            <v-btn
              icon
              rounded="circle"
              size="large"
              :href="'https://www.linkedin.com/in/timcarrender/'"
              target="_blank"
              class="social-btn"
            >
              <v-icon size="28">mdi-linkedin</v-icon>
            </v-btn>
          </div>
        </div>
      </v-container>
    </v-main>
  </v-layout>
</template>

<script setup>

</script>

<style scoped>
/* Hero Section */
.hero-section {
  position: relative;
}

.hero-image {
  filter: brightness(0.7); /* Slightly darken the image for better contrast */
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.8)); /* Gradient overlay for better text visibility */
}

/* Profile Container */
.profile-container {
  margin-top: -120px; /* Pull the profile card up to overlap the hero image */
  display: flex;
  justify-content: center;
}

/* Profile Card */
.profile-card {
  background: rgba(20, 20, 20, 0.95); /* Dark semi-transparent background */
  border-radius: 16px;
  padding: 32px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
  text-align: center;
  max-width: 800px;
  width: 100%;
  transition: transform 0.3s ease;
}

.profile-card:hover {
  transform: translateY(-5px);
}

/* Avatar Styling */
.profile-avatar {
  border: 4px solid #0288d1; /* Add a primary color border */
  margin-bottom: 16px;
  transition: transform 0.3s ease;
}

.profile-avatar:hover {
  transform: scale(1.05);
}

/* Buttons */
.action-btn {
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 1px;
  transition: all 0.3s ease;
}

.action-btn:hover {
  transform: scale(1.03);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

.social-btn {
  background-color: #0288d1;
  color: white;
  transition: all 0.3s ease;
}

.social-btn:hover {
  background-color: #0277bd;
  transform: scale(1.1);
}

/* Adjust spacing for profile logos */
.d-flex.flex-wrap.justify-center.gap-3 {
  gap: 16px; /* Increase spacing between buttons */
}

/* Responsive Adjustments */
@media (max-width: 600px) {
  .profile-card {
    padding: 24px;
  }

  .text-h3 {
    font-size: 1.75rem !important;
  }

  .action-btn {
    width: 100%;
    margin-bottom: 8px;
  }
}
</style>