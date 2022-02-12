<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app stateless>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Menu</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Bon Voyage</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  data: () => ({
    drawer: null,
    items: [
      {
        title: 'Home',
        icon: 'mdi-home',
        to: '/',
      },
      {
        title: 'About',
        icon: 'mdi-information',
        to: '/about',
      },
    ],
  }),
});
</script>
