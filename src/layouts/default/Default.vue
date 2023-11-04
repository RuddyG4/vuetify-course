<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar title="Application bar" density="comfortable" :color="`#0f0f0f`" :elevation="8">
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

    <v-navigation-drawer>
      <v-list>
        <v-list-item title="Navigation drawer"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main class="d-flex align-center justify-center" style="min-height: 300px;">
      <router-view></router-view>
    </v-main>
  </v-layout>
</template>