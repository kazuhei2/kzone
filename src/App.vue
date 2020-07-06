<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
    <v-container>
      <v-list dense nav>
        <v-list-item
          v-for="item in navList"
          :key="item.name"
          :to="item.link"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.name }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-container>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />
      </div>
      <v-toolbar-title>kzone</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <v-container>
        <router-view/>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  components: {
  },

  data: () => ({
    drawer: null,
    navList: [
      {
        name: 'Home',
        icon: 'mdi-home',
        link: '/'
      },
      {
        name: 'About',
        icon: 'mdi-information',
        link: '/about'
      },
      {
        name: 'DevelopersRoom',
        icon: 'mdi-android-debug-bridge',
        link: '/developers-room'
      },
    ],
  }),

  methods: {
  },
};
</script>
