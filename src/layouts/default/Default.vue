<script lang="ts" setup>
  import { ref } from 'vue';
  const drawer = ref(true);
</script>

<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar density="comfortable" :color="`#0f0f0f`" :elevation="8">
      <template #prepend>
        <v-app-bar-nav-icon variant="text" @click="drawer = !drawer">

        </v-app-bar-nav-icon>
        <v-toolbar-title>
          <router-link to="/" class="text-decoration-none text-white">
            Vuetify Course
          </router-link>
        </v-toolbar-title>
      </template>
      <template #append>
        <v-menu>
          <template v-slot:activator="{ props }">
            <v-avatar v-bind="props" image="https://avatars.githubusercontent.com/u/95689617?v=4"></v-avatar>
          </template>
          <v-list>
            <v-list-item v-for="(item, index) in ['profile', 'settings', 'logout']" :key="index" :value="index">
              <v-list-item-title>{{ item }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </template>
    </v-app-bar>

    <v-navigation-drawer expand-on-hover rail v-model="drawer">
      <v-list>
        <v-list>
          <v-list-item prepend-avatar="https://avatars.githubusercontent.com/u/95689617?v=4" title="Gonzalo Quispe"
            subtitle="ruddygonzqh@gmailcom"></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-post-outline" title="Posts" :to="`/posts`" value="myfiles"></v-list-item>
          <v-list-item prepend-icon="mdi-comment-outline" title="Comments" :to="`/comments`" value="shared"></v-list-item>
        </v-list>
      </v-list>
    </v-navigation-drawer>

    <v-main class="d-flex align-center justify-center" style="min-height: 300px;">
      <router-view></router-view>
    </v-main>
  </v-layout>
</template>