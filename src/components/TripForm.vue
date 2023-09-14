<template>
    <v-container>
      <v-form ref="form">
        <!-- Name Field -->
        <v-text-field v-model="name" label="Name" required></v-text-field>
  
        <!-- From Date Field -->
        <v-date-picker v-model="fromDate" label="From Date"></v-date-picker>
  
        <!-- To Date Field -->
        <v-date-picker v-model="toDate" label="To Date"></v-date-picker>
  
        <!-- Note Field -->
        <v-text-field v-model="note" label="Note" required></v-text-field>
  
        <!-- Submit Button -->
        <v-btn @click="submitForm">Submit</v-btn>
      </v-form>
    </v-container>
  </template>
  
  <script lang="ts">
  import { ref } from 'vue';
  
  export default {
    name: 'TripForm',
    setup() {
      const name = ref('');
      const fromDate = ref(null);
      const toDate = ref(null);
      const note = ref('');
  
      const submitForm = () => {
        console.log({
          name: name.value,
          from: `${fromDate.value}`,
          to: `${toDate.value}`,
          note: note.value,
        });
      };
  
      return {
        name,
        fromDate,
        toDate,
        note,
        submitForm,
      };
    },
  };
  </script>
  