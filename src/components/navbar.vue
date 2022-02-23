<template>
  <v-card>
    <v-toolbar color="deep-purple accent-4" dark flat tile >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Page title</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon><v-icon>mdi-magnify</v-icon></v-btn>

      <v-btn icon> <v-icon>mdi-dots-vertical</v-icon></v-btn>

    </v-toolbar>
  </v-card>
</template>

<script>
  export default {
    name: 'Navbar',
    data: () => ({
      currentItem: 'tab-Web',
    }),
  }
</script>