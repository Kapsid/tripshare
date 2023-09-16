<template>
  <v-container>
    <v-form ref="form">
      <!-- Main Name Field -->
      <v-text-field v-model="mainName" label="Main Name" required></v-text-field>
      <!-- Main Description Field -->
      <v-text-field v-model="mainDescription" label="Description"></v-text-field>
      
      <!-- Items -->
      <div v-for="(item, index) in items" :key="index">
        <v-text-field v-model="item.name" label="Item Name"></v-text-field>
        <v-text-field v-model="item.description" label="Item Description"></v-text-field>
        <v-date-picker v-model="item.fromDate" label="From Date"></v-date-picker>
        <v-time-picker v-model="item.fromTime" label="From Time"></v-time-picker>
        <v-date-picker v-model="item.toDate" label="To Date"></v-date-picker>
        <v-time-picker v-model="item.toTime" label="To Time"></v-time-picker>
        <v-btn icon @click="removeItem(index)">
          <v-icon>mdi-minus</v-icon>
        </v-btn>
      </div>

      <!-- PLUS Button -->
      <v-btn @click="addItem">
        <v-icon>mdi-plus</v-icon>
      </v-btn>

      <!-- Global Submit Button -->
      <v-btn @click="submitForm">Submit</v-btn>
    </v-form>
  </v-container>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue';

interface Item {
  name: string;
  description: string;
  fromDate: string | null;
  fromTime: string | null;
  toDate: string | null;
  toTime: string | null;
}

export default defineComponent({
  name: 'ComplexForm',
  setup() {
    const mainName = ref('');
    const mainDescription = ref('');
    const items = ref<Item[]>([]);

    const addItem = () => {
      items.value.push({
        name: '',
        description: '',
        fromDate: null,
        fromTime: null,
        toDate: null,
        toTime: null,
      });
    };

    const removeItem = (index: number) => {
      items.value.splice(index, 1);
    };

    const submitForm = () => {
      console.log({
        mainName: mainName.value,
        mainDescription: mainDescription.value,
        items: items.value,
      });
    };

    return {
      mainName,
      mainDescription,
      items,
      addItem,
      removeItem,
      submitForm,
    };
  },
});
</script>