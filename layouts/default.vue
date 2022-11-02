<template>
  <v-app>
    <v-app-bar color="primary">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Nuxt 3 & Vuetify 3 Template</v-toolbar-title>

      <v-toolbar color="primary">
        <MenuInbox />
        <MenuNotification />
        <MenuUser />
      </v-toolbar>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer">
      <template v-slot:prepend>
        <v-list-item
          lines="two"
          prepend-avatar="https://randomuser.me/api/portraits/women/81.jpg"
          title="Jane Smith"
          subtitle="Logged in"
        ></v-list-item>
      </template>

      <v-divider></v-divider>
      <v-list
        density="compact"
        nav
      >
        <v-list-item prepend-icon="mdi-view-dashboard" title="Home" value="home" to="/"></v-list-item>
        <v-list-item prepend-icon="mdi-forum" title="About" value="about" to="/about"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container fluid>
        <NuxtPage />
      </v-container>
      <v-footer height="auto" class="white pa-3 app--footer">
        <span class="caption">HuynhDN Footer &copy; 2022</span>
        <v-spacer />
        <v-icon color="pink" small>
          mdi-heart
        </v-icon>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script lang="ts">
export default {
  data: () => ({
    drawer: null,
  }),
};
</script>