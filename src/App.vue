<template>
  <v-app>
      <!-- navbar -->
      <v-app-bar app color="primary" dark>
          <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
          <v-spacer />
          <v-btn 
              v-for="link in links"
              :key="`${link.label}-header-link`"
              text
              rounded 
              :to="link.url"
              >
              {{ link.label }}
          </v-btn>
          <v-btn @click="toggleTheme" text rounded>Toggle Theme</v-btn>
      </v-app-bar>
      <v-content>
          <router-view />
      </v-content>
      <!-- footer -->
      <v-footer app color="primary lighten-1" dark padless>
          <v-layout justify-center wrap>
              <v-btn
                  v-for="link in links"
                  :key="`${link.label}-footer-link`"
                  color="white"
                  text
                  rounded
                  class="my-2"
                  :to="link.url"
              >
              {{ link.label }}
              </v-btn>
              <v-flex primary lighten-2 py-4 text-center white--text xs12>
                  {{ new Date().getFullYear() }} - <strong>Vuetify Dashboard</strong>
              </v-flex>
          </v-layout>
      </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
      links: [
          {
              label: 'Home',
              url: '/'
          },
          {
              label: 'Login',
              url: '/login'
          },
          {
              label: 'Signup',
              url: '/signup'
          },
          {
              label: 'Dashboard',
              url: '/dashboard'
          },
      ] 
  }),
    methods: {
        toggleTheme() {
            this.$vuetify.theme.dark =!this.$vuetify.theme.dark
        }
    }
};
</script>
