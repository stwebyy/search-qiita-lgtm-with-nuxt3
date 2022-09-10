<template>
  <v-layout>
    <!-- <v-system-bar color="deep-purple darken-3"></v-system-bar> -->

    <v-app-bar color="primary">
      <v-app-bar-nav-icon
        variant="text"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <v-toolbar-title>TODO</v-toolbar-title>

      <v-spacer></v-spacer>

      <!-- TODO: ユーザー関連の -->
      <v-btn variant="text" icon="mdi-dots-vertical"></v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" bottom temporary>
      <v-list dense>
        <v-list-item-group>
          <v-list-item v-for="(item, i) in items" :key="i" :to="item.link">
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
              <v-list-item-content>
                {{ item.title }}
              </v-list-item-content>
            </v-list-item-action>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <slot />
    </v-main>
  </v-layout>
</template>
<script setup lang="ts">
const drawer = ref(false);
const items = [
  {
    title: 'Foo',
    icon: 'mdi-chevron-right',
    link: 'aaa',
  },
  {
    title: 'Bar',
    icon: 'bar',
    link: 'bbb',
  },
  {
    title: 'Fizz',
    icon: 'fizz',
    link: 'ccc',
  },
  {
    title: 'Buzz',
    icon: 'buzz',
    link: 'ddd',
  },
];
</script>
