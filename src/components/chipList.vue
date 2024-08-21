<template>
  <div>
    <q-chip
      v-for="chip in chips"
      :key="chip.text"
      :color="chip.color"
      text-color="white"
    >
      <q-icon style="margin-right: 5px"> <q-img :src="chip.image" /> </q-icon>
      {{ chip.text }}
    </q-chip>
  </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

// Define the type for chip data
interface Chip {
  color: string;
  text: string;
  image?: string;
}

// Define the props for the component
const props = defineProps<{
  chips: Chip[];
}>();
</script>

<style scoped>
/* Add any additional styling if necessary */
</style>
