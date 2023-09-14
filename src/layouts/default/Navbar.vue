<template theme="light">
    <v-app-bar class="navbar" :density="compact">
      <v-container>
        <v-btn to="/form">Form</v-btn>
        <v-btn to="/trip">Trip</v-btn>
        <v-btn to="/profile">Profile</v-btn>
        <v-btn to="/inspire">Inspire</v-btn>
      </v-container>
    </v-app-bar>
</template>

<style scoped>
.v-btn{
    color: #EEA46C;
}
</style>