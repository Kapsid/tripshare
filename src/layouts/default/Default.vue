<template>
  <v-app>
    <navbar></navbar>
    <default-view />
  </v-app>
</template>

<script lang="ts" setup>
  import DefaultBar from './AppBar.vue'
  import DefaultView from './View.vue'
  import Navbar from './Navbar.vue'
</script>
